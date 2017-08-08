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
public class StringUtils {

	public static String leftPad(String str, int size) { return org.apache.commons.lang3.StringUtils.leftPad(str, size); };
	public static String leftPad(String str, int size, char padChar) { return org.apache.commons.lang3.StringUtils.leftPad(str, size, padChar); };
	public static String leftPad(String str, int size, String padChar) { return org.apache.commons.lang3.StringUtils.leftPad(str, size, padChar); };
	
	// 1.7 corrected. these were left-padding.
	public static String rightPad(String str, int size) { return org.apache.commons.lang3.StringUtils.rightPad(str, size); };
	public static String rightPad(String str, int size, char padChar) { return org.apache.commons.lang3.StringUtils.rightPad(str, size, padChar); };
	public static String rightPad(String str, int size, String padChar) { return org.apache.commons.lang3.StringUtils.rightPad(str, size, padChar); };

	// 1.6
	public static int countMatches(CharSequence str, char ch) { return org.apache.commons.lang3.StringUtils.countMatches(str, ch); };
	public static int countMatches(CharSequence str, CharSequence sub) { return org.apache.commons.lang3.StringUtils.countMatches(str, sub); };
}
