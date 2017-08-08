/*
 Copyright 2015, 2016, Yellow Pelican Ltd. www.YellowPelican.co.uk

 Licensed under the Apache License, Version 2.0 (the "License");
 you may not use this file except in compliance with the License.
 You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing, software
 distributed under the License is distributed on an "AS IS" BASIS,
 WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
 See the License for the specific language governing permissions and
 limitations under the License.
*/
package routines;

/*
 * Framework Class.
 */
public class Framework {
	
	// 1.5
	private static String homeDir = FileHelper.normalizeNoEndSeparator(System.getProperty("user.home"));

	private String frameworkVersion = "1.7";
	private String frameworkAuthor = "Alan.Black@YellowPelican.co.uk";
	private String contextStr = "Default";
	private String baseDir = String.format("%s/talend/project/%s", getHomeDir(), contextStr);
	private String projectName = "NOPROJECT";
	private String jobName = "NOJOB";
	private String jobVersion = "0.0";
	private java.util.Date startTime = TalendDate.getCurrentDate();
	private String startTimeStr = TalendDate.formatDate("yyyyMMdd.HHmmss", startTime);

	// 1.7
	private java.util.concurrent.ConcurrentHashMap<String, Object> sharedMap = new java.util.concurrent.ConcurrentHashMap<String, Object>();
	private String priorityErrorRecipient = null;
	private String processingErrorRecipient = null;
	
	/**
	 * Initialises the Framework.
	 * 
	 * @param baseDir
	 * @param projectName
	 * @param jobName
	 * @param jobVersion
	 */
	public Framework(String baseDir, String contextStr, String projectName, String jobName, String jobVersion) {
		if(FieldHelper.isNotEmpty(projectName)) this.projectName = projectName;
		if(FieldHelper.isNotEmpty(jobName)) this.jobName = jobName;
		if(FieldHelper.isNotEmpty(jobVersion)) this.jobVersion = jobVersion;
		if(FieldHelper.isNotEmpty(contextStr)) this.contextStr = replaceContextTokens(contextStr);
		// 1.5
		if(FieldHelper.isNotEmpty(baseDir)) this.baseDir = FileHelper.normalizeNoEndSeparator(replaceContextTokens(baseDir));
		
		// 1.7
		sharedMapPut("Framework.Orchestration.Execute.Next", true);
		sharedMapPut("Framework.Last.Error.Message", "");
	}

	/**
	 * 
	 * @return
	 */
	public String getFrameworkVersion() { return frameworkVersion; };

	/**
	 * 
	 * @return
	 */
	public String getFrameworkAuthor() { return frameworkAuthor; };
	
	/**
	 * 
	 * @return
	 */
	public java.util.Date getStartTime() {
		return startTime;
	}

	/**
	 * 
	 * @return
	 */
	public String getStartTimeStr() {
		return startTimeStr;
	}

	/**
	 * 
	 * @param jobName
	 * @param message
	 */
	public void errorMessage(String jobName, String message) {
		System.err.println(String.format("%s: %s, jobName, message"));
	}
	
	/**
	 * 
	 * @param jobName
	 * @param jobVersion
	 * @param messageTime
	 * @param message
	 */
	public void message(String jobName, String jobVersion, java.util.Date messageTime, String message)
	{
		System.out.println(jobName + ": " + jobVersion + ": " + message + ": " + messageTime);		
	}
	
	/**
	 * 
	 * @param jobName
	 * @param jobVersion
	 * @param message
	 */
	public void message(String jobName, String jobVersion, String message) {
		message(jobName, jobVersion, TalendDate.getCurrentDate(), message);
	}
	
	/**
	 * 
	 * @param messageTime
	 * @param message
	 */
	public void message(java.util.Date messageTime, String message) {
		message(jobName, jobVersion, messageTime, message);
	}
		
	/**
	 * 
	 * @param message
	 * @return
	 */
	public void message(String message) {
		message(TalendDate.getCurrentDate(), message);
	}


	/**
	 * Returns the Home Directory.
	 * 
	 * @return
	 */
	public static String getHomeDir() {
		return homeDir;
	}

	/**
	 * Sets the Base Directory.
	 * 
	 * @param baseDir
	 */
	public void setBaseDir(String baseDir) {
		// 1.5
		if(FieldHelper.isNotEmpty(baseDir)) FileHelper.normalizeNoEndSeparator(this.baseDir = baseDir);
	}
	
	/**
	 * Returns the Base Directory.
	 * 
	 * @return
	 */
	public String getBaseDir() {
		return baseDir;
	}

	/**
	 * Returns the Project Name.
	 * 
	 * @return
	 */
	public String getProjectName() {
		return projectName;
	}

	/**
	 * Returns the Context String.
	 * 
	 * @return
	 */
	public String getContextStr() {
		return contextStr;
	}

	/**
	 * Returns the Job Name.
	 * 
	 * @return
	 */
	public String getJobName() {
		return jobName;
	}
	
	/**
	 * Returns the Job Version.
	 *  	
	 * @return
	 */
	public String getJobVersion() {
		return jobVersion;
	}

	/**
	 * Parses the supplied String and replaces the Context Tokens.
	 *
	 * @param value
	 * @param baseDir
	 * @param projectName
	 * @param jobName
	 * @return
	 */
	public static String replaceContextTokens(String value, String baseDir, String contextStr, String projectName, String jobName) {
		if(value == null) return value;
		else {
			return value.replace("#HOME", getHomeDir()).
			 			 // 1.5
						 replace("#BASEDIR", (baseDir == null ? "#BASEDIR" : FileHelper.normalizeNoEndSeparator(baseDir))).
 						 replace("#PROJECTNAME", projectName).
 						 replace("#CONTEXTSTR", contextStr).
			 			 replace("#JOBNAME", jobName);
		}
	}
	
	/**
	 * Parses the supplied String and replaces the Context Tokens.
	 *  
	 * @param value
	 * @return
	 */
	public String replaceContextTokens(String value) {
		return replaceContextTokens(value, baseDir, contextStr, projectName, jobName);
	}

	/**
	 * Parses the supplied String and replaces the Context Tokens.
	 *  
	 * @param value
	 * @param baseDir
	 * @return
	 */
	public String replaceContextTokens(String value, String baseDir) {
		// 1.5
		return replaceContextTokens(value, (FieldHelper.isEmpty(baseDir) ? this.baseDir : FileHelper.normalizeNoEndSeparator(baseDir)), contextStr, projectName, jobName);
	}
	
	
	/**
	 * 
	 * @param statsDir
	 * @param projectName
	 * @param jobName
	 * @return
	 */
	public static String getDefaultStatsDir(String statsDir, String baseDir, String contextStr, String projectName, String jobName) {		

		String retVal = null;
		
		/*
		 * If no statsDir is passed, determine from supplied parameters.
		 */
		// 1.5
		if(FieldHelper.isEmpty(statsDir)) {
			//System.err.println("Framework.getDefaultStatsDir: baseDir: " + baseDir);

			/*
			 * If no baseDir is supplied, use default.
			 */
			// 1.5
			if(FieldHelper.isEmpty(baseDir)) {
				retVal = String.format("%s/talend/project/%s/%s/%s/stats", getHomeDir(), contextStr, projectName, jobName);
			}
			else {
				//retVal = replaceContextTokens(String.format("%s/%s/%s/%s/stats", baseDir, contextStr, projectName, jobName), baseDir, contextStr, projectName, jobName);
				// 1.5
				retVal = replaceContextTokens(String.format("%s/stats", FileHelper.normalizeNoEndSeparator(baseDir)), FileHelper.normalizeNoEndSeparator(baseDir), contextStr, projectName, jobName);
				//System.out.println("   ***getDefaultStatsDir: " + retVal);
			}
		}
		
		/*
		 * We have a statsDir, so parse, using supplied parameters.
		 * 
		 * We do expect statsDir to specify its own baseDir, or use #BASEDIR.
		 */
		else {
				//System.err.println("getDefaultStatsDir: " + statsDir);
				// 1.5
				retVal = replaceContextTokens(FileHelper.normalizeNoEndSeparator(statsDir), replaceContextTokens(FileHelper.normalizeNoEndSeparator(baseDir), String.format("%s/talend/project/%s", getHomeDir(), contextStr), contextStr, projectName, jobName), contextStr, projectName, jobName);
		}
		
		//System.err.println("getDefaultStatsDir: " + retVal);
		//System.err.println("Framework.getDefaultStatsDir: " + retVal);
		return retVal;
	}
	
	/**
	 * 
	 * @return
	 */
	public java.util.Map<String, Object> getSharedMap() {
		return (java.util.Map<String, Object>) sharedMap;
	}
	
	/**
	 * 
	 * @param key
	 * @param value
	 */
	public void sharedMapPut(String key, Object value) {
		((java.util.Map<String, Object>) sharedMap).put(key, value);
	}

	/**
	 * 
	 * @param key
	 * @return
	 */
	public Object sharedMapGet(String key) {
		return ((java.util.Map<String, Object>) sharedMap).get(key);
	}
	
	/**
	 * 
	 * @param key
	 * @return
	 */
	public Integer sharedMapGetAsInteger(String key) {
		try {
			return ((Integer) ((java.util.Map<String, Object>) sharedMap).get(key));
		}
		catch (ClassCastException e) {
			return null;
		}
	}
	
	/**
	 * 
	 * @param key
	 * @return
	 */
	public String sharedMapGetAsString(String key) {
		try {
			return ((String) ((java.util.Map<String, Object>) sharedMap).get(key));
		}
		catch (ClassCastException e) {
			return null;
		}
	}
	
	/**
	 * 
	 * @param key
	 * @return
	 */
	public Boolean sharedMapGetAsBoolean(String key) {
		try {
			return ((Boolean) ((java.util.Map<String, Object>) sharedMap).get(key));
		}
		catch (ClassCastException e) {
			return null;
		}
	}

	/**
	 * 
	 * @param key
	 * @return
	 */
	public java.util.Date sharedMapGetAsDate(java.util.Date key) {
		try {
			return ((java.util.Date) ((java.util.Map<String, Object>) sharedMap).get(key));
		}
		catch (ClassCastException e) {
			return null;
		}
	}
	
	/**
	 * 
	 * @param key
	 * @return
	 */
	public java.math.BigDecimal sharedMapGetAsBigDecimal(java.math.BigDecimal key) {
		try {
			return ((java.math.BigDecimal) ((java.util.Map<String, Object>) sharedMap).get(key));
		}
		catch (ClassCastException e) {
			return null;
		}
	}

	/**
	 * 
	 * @param message
	 */
	public void jobErrorMessageClear() {
		sharedMapPut("Framework.Last.Error.Message", "");
	}

	/**
	 * 
	 * @param message
	 */
	public void jobErrorMessageSet(String message) {
		if(FieldHelper.isEmpty(message)) sharedMapPut("Framework.Last.Error.Message", "");
		else sharedMapPut("Framework.Last.Error.Message", message);
	}
	
	/**
	 * 
	 * @param message
	 */
	public void jobErrorMessageAppend(String message) {
		if(FieldHelper.isEmpty(message)) return;
		else {
			if(FieldHelper.isEmpty(jobErrorMessageGet())) jobErrorMessageSet(message);
			else sharedMapPut("Framework.Last.Error.Message",
					  		  String.format("%s\n%s",
					  				  		sharedMapGetAsString("Framework.Last.Error.Message"),
											message));
		}
	}
	
	/**
	 * 
	 * @return
	 */
	public String jobErrorMessageGet() {
		return sharedMapGetAsString("Framework.Last.Error.Message");
	}

	/**
	 * 
	 * @param systemErrorRecipient
	 * @param sendMailTo
	 * @param processingErrorRecipient
	 */
	public void setErrorRecipient(String systemErrorRecipient, String sendMailTo, String processingErrorRecipient) {
		
		/*
		System.err.println("systemErrorRecipient: " + systemErrorRecipient);
		System.err.println("sendMailTo: " + sendMailTo);
		System.err.println("processingErrorRecipient: " + processingErrorRecipient);
		*/
		
		if(FieldHelper.isNotEmpty(systemErrorRecipient)) priorityErrorRecipient = systemErrorRecipient;
		else if(FieldHelper.isNotEmpty(sendMailTo)) priorityErrorRecipient = sendMailTo;
		else if(FieldHelper.isNotEmpty(processingErrorRecipient)) priorityErrorRecipient = processingErrorRecipient;
		else priorityErrorRecipient = null;

		if(FieldHelper.isNotEmpty(processingErrorRecipient)) this.processingErrorRecipient = processingErrorRecipient;
		else if(FieldHelper.isNotEmpty(systemErrorRecipient)) this.processingErrorRecipient = systemErrorRecipient;
		else if(FieldHelper.isNotEmpty(sendMailTo)) this.processingErrorRecipient = sendMailTo;
		else this.processingErrorRecipient = null;
		
		/*
		System.err.println("priorityErrorRecipient: " + priorityErrorRecipient);
		System.err.println("this.processingErrorRecipient: " + this.processingErrorRecipient);
		*/
	}

	/**
	 * 
	 * @return
	 */
	public String getPriorityErrorRecipient() {
		return priorityErrorRecipient;
	}
	
	/**
	 * 
	 * @return
	 */
	public String getProcessingErrorRecipient() {
		return processingErrorRecipient;
	}
	
	/**
	 * 
	 * @param systemErrorRecipient
	 * @param sendMailTo
	 * @param processingErrorRecipient
	 * @return
	 */
	public static String getBestErrorRecipient(String list1, String list2, String list3) {
		if(FieldHelper.isNotEmpty(list1)) return list1;
		else if(FieldHelper.isNotEmpty(list2)) return list2;
		else if(FieldHelper.isNotEmpty(list3)) return list3;
		else return null;
	}
}