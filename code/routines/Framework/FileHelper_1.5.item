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
public class FileHelper {

	/**
	 * Makes an acceptable file name, from th passed text.
	 * 
	 * @param value
	 * @return
	 */
	public static String makeFileName(String value) {
		if(FieldHelper.isEmpty(value)) return "file_name";
		else return value.replaceAll("[^a-zA-Z0-9.-]", "_").replaceAll("_+", "_");
	}
	
	public static String makeFileName(String value, String ext) {
		if(FieldHelper.isEmpty(ext)) return makeFileName(value);
		else return String.format("%s.%s", makeFileName(value), ext.replaceAll("^\\.", ""));
	}
	
	/*
	 * org.apache.commons.io.FilenameUtils wrappers
	 */
	public static String getFullPath(String filename) {
		return org.apache.commons.io.FilenameUtils.getFullPath(filename); 
	}

	public static String getFullPathNoEndSeparator(String filename) {
		return org.apache.commons.io.FilenameUtils.getFullPathNoEndSeparator(filename); 
	}

	public static String getBaseName(String filename) {
		return org.apache.commons.io.FilenameUtils.getBaseName(filename); 
	}

	public static String normalize(String filename) {
		return org.apache.commons.io.FilenameUtils.normalize(filename); 
	}

	public static String normalizeNoEndSeparator(String filename) {
		return org.apache.commons.io.FilenameUtils.normalizeNoEndSeparator(filename); 
	}

	public static String removeExtension(String filename) {
		return org.apache.commons.io.FilenameUtils.removeExtension(filename); 
	}
	
	public static String addExtension(String filename, String extension) {
		if(FieldHelper.isEmpty(filename)) return null;
		else if(FieldHelper.isEmpty(extension)) return filename;
		else if(extension.substring(0, 1).equals(".")) return String.format("%s%s", filename, extension);
		else return String.format("%s.%s", filename, extension);
	}
	
	public static String changeExtension(String filename, String extension) {
		if(FieldHelper.isEmpty(filename)) return null;
		else if(FieldHelper.isEmpty(extension)) return filename;
		else if(extension.substring(0, 1).equals(".")) return String.format("%s%s", FileHelper.removeExtension(filename), extension);
		else return String.format("%s.%s", FileHelper.removeExtension(filename), extension);
	}
}