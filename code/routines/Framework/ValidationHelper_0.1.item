/*
 Copyright 2015, Yellow Pelican Ltd. www.YellowPelican.co.uk

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
 * user specification: the function's comment should contain keys as follows: 1. write about the function's comment.but
 * it must be before the "{talendTypes}" key.
 * 
 * 2. {talendTypes} 's value must be talend Type, it is required . its value should be one of: String, char | Character,
 * long | Long, int | Integer, boolean | Boolean, byte | Byte, Date, double | Double, float | Float, Object, short |
 * Short
 * 
 * 3. {Category} define a category for the Function. it is required. its value is user-defined .
 * 
 * 4. {param} 's format is: {param} <type>[(<default value or closed list values>)] <name>[ : <comment>]
 * 
 * <type> 's value should be one of: string, int, list, double, object, boolean, long, char, date. <name>'s value is the
 * Function's parameter name. the {param} is optional. so if you the Function without the parameters. the {param} don't
 * added. you can have many parameters for the Function.
 * 
 * 5. {example} gives a example for the Function. it is optional.
 */
public class ValidationHelper {

	/**
	 * We're looking for patterns that suggest that this is not a Job Title.
	 * 
	 * @param jobTitle
	 * @return
	 */
	public static Boolean isJobTitle(String jobTitle) {
		if(jobTitle == null) return true;
		else {
			String testVal = jobTitle.toUpperCase();
			
			if(testVal.matches(".*\\bPLC\\b.*") ||
			   testVal.matches(".*\\bLIMITED\\b.*") ||
			   testVal.matches(".*\\bLLP\\b.*") ||
			   testVal.matches(".*\\bBERHAD\\b.*") ||
			   testVal.matches(".*\\bBHD\\b.*") ||
			   testVal.matches(".*\\bLTD\\b.*")) return false;
			else return true;
		}
	}
	
	/**
	 * We're looking for patterns that suggest that this is not a Company Name.
	 * 
	 * @param companyName
	 * @return
	 */
	public static Boolean isCompanyName(String companyName) {
		if(companyName == null) return true;
		else {
			String testVal = companyName.toUpperCase();
			
			if(testVal.matches(".*\\bDIRECTOR\\b.*") ||
			   testVal.matches(".*\\bMD\\b.*") ||
			   testVal.matches(".*\\bASSOCIATE\\b.*") ||
			   testVal.matches(".*\\bSECRETARY\\b.*") ||
			   testVal.matches(".*\\bEXECUTIVE\\b.*") ||
			   testVal.matches(".*\\bPARTNER\\b.*") ||
			   testVal.matches(".*\\bSVP\\b.*") ||
			   testVal.matches(".*\\bCEO\\b.*") ||
			   testVal.matches(".*\\bLEADER\\b.*") ||
			   testVal.matches(".*\\bLECTURER\\b.*")) return false;
			else return true;
		}
	}
	
	/**
	 * For the purposes of our validation, we will consider a null value as being valid.
	 * 
	 * @param emailAddress
	 * @return
	 */
    public static Boolean isEmailAddress(String emailAddress) {
    	if(emailAddress == null || "".equals(emailAddress.trim())) return true;
    	else {
    		return org.apache.commons.validator.routines.EmailValidator.getInstance().isValid(emailAddress);
    		//if(emailAddress.matches("^[\\w\\.-]+@([\\w\\-]+\\.)+[A-Za-z]{2,4}$")) return true;
    		//else return false;
    	}
    }
}
