/*
 Copyright 2015, 2016 Yellow Pelican Ltd. www.YellowPelican.co.uk

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

import java.util.UUID;

/**
 * This Class contains a number of static methods, for dealing with values (fields), including a number of
 * null-safe methods.
 * 
 * These methods recognises the String "null" as representing null, and all white-space values are considered null.
 * Whenever String conversions take place, null will be returned rather than "null" or whitespace.
 */
public class FieldHelper {

	/**
	 * 
	 * @param field
	 * @return
	 */
    public static boolean isEmpty(String field) {
    	if(field == null || "".equals(field.trim()) || "null".equals(field.trim())) return true;
    	else return false;
    }
    
    /**
     * 
     * @param field
     * @return
     */
    public static boolean isNotEmpty(String field) {
    	return ! isEmpty(field);
    }
    
    public static String nullify(String field) {
    	if(isEmpty(field)) return null;
    	else return field;
    }

    /**
     * 
     * @param field
     * @return
     */
    public static String toUpperCase(String field) {
    	if(isEmpty(field)) return null;
    	else return field.toUpperCase();
    }

    /**
     * 
     * @param field
     * @return
     */
    public static String toLowerCase(String field) {
    	if(isEmpty(field)) return null;
    	else return field.toLowerCase();
    }

    /**
     * 
     * @param field
     * @param length
     * @return
     */
    public static String truncateAt(String field, int length) {
    	if(isEmpty(field)) return null;
    	else if(field.length() <= length) return field;
    	else return field.substring(0, length);
    }
    
    /**
     * 
     * @param field
     * @param characters
     * @return
     */
    public static String strip(String field, String characters) {
    	if(isEmpty(field)) return null;
    	else return field.replaceAll(characters, "");
    }

    /**
     * 
     * @param field
     * @param characters
     * @param replacementCharacters
     * @return
     */
    public static String replaceAll(String field, String characters, String replacementCharacters) {
    	if(isEmpty(field)) return null;
    	else return field.replaceAll(characters, replacementCharacters);
    }

    /**
     * 
     * @param field1
     * @param field2
     * @return
     */
    public static boolean isDifferent(String field1, String field2) {
    	if(field1 == null & field2 == null) return false;
    	else if(field1 == null) return true;
    	else if(field1.equals(field2)) return false;
    	else return true;
    }
    
    /**
     * 
     * @param field1
     * @param field2
     * @return
     */
    public static boolean isDifferent(java.util.Date field1, java.util.Date field2) {
    	if(field1 == null & field2 == null) return false;
    	else if(field1 == null) return true;
    	else if(field1.equals(field2)) return false;
    	else return true;
    }
    
    /**
     * 
     * @param field1
     * @param field2
     * @return
     */
    public static boolean isDifferent(java.math.BigDecimal field1, java.math.BigDecimal field2) {
    	if(field1 == null & field2 == null) return false;
    	else if(field1 == null) return true;
    	else if(field1.equals(field2)) return false;
    	else return true;
    }
    
    /**
     * 
     * @param field1
     * @param field2
     * @return
     */
    public static boolean isEqual(String field1, String field2) {
    	return ! isDifferent(field1, field2);
    }

    /**
     * Safely parses an Integer, return null if the string integer cannot be parsed.
     * 
     * @param pattern
     * @param stringDate
     * @param verbose
     * @return
     */
    public static Integer parseIntegerSafe(String stringInteger, Boolean verbose) {
    	
    	// 1.6 Tested for empty so that we do not report this in debug mode.
    	if(isEmpty(stringInteger)) return null;
    	else {
    		try {
    			return new Integer(stringInteger);
    		}
    		catch (Exception e) {
    			if(verbose) System.err.println("FieldHelper.parseIntegerSafe: unparseable Integer: " + stringInteger);
    			return null;
    		}
    	}
    }
    
    /**
     * 
     * @param pattern
     * @param stringInteger
     * @return
     */
    public static Integer parseIntegerSafe(String stringInteger) {
    	return parseIntegerSafe(stringInteger, false);
    }
    
    
    
    /**
     * Safely parses a Date, return null if the string date cannot be parsed.
     * 
     * @param pattern
     * @param stringDate
     * @param verbose
     * @return
     */
    public static java.util.Date parseDateSafe(String pattern, String stringDate, Boolean verbose) {
    	
    	// 1.7
    	if(FieldHelper.isEmpty(stringDate)) return null;
    	else {
    		try {
    			return TalendDate.parseDate(pattern, stringDate);
    		}
    		catch (Exception e) {
    			if(verbose) System.err.println("FieldHelper.parseDateSafe: unparseable Date: " + stringDate + " using pattern " + pattern);
    			return null;
    		}
    	}
    }
    
    /**
     * 
     * @param pattern
     * @param stringDate
     * @return
     */
    public static java.util.Date parseDateSafe(String pattern, String stringDate) {
    	return parseDateSafe(pattern, stringDate, false);
    }
    
    /**
     * 
     * @param field1
     * @param field2
     * @return
     */
    public static boolean isEqual(java.util.Date field1, java.util.Date field2) {
    	return ! isDifferent(field1, field2);
    }
    
    /**
     * 
     * @param field1
     * @param field2
     * @return
     */
    public static boolean isEqual(java.math.BigDecimal field1, java.math.BigDecimal field2) {
    	return ! isDifferent(field1, field2);
    }
    
    /**
     * Safely parses a BigDecimal, return null if the string date cannot be parsed.
     *
     * @param stringBigDecimal
     * @param verbose
     * @return
     */
    public static java.math.BigDecimal parseBigDecimalSafe(String stringBigDecimal, Boolean verbose) {
    	
    	/*
    	 * 1.7.1
    	 * 
    	 * It is dangerous to simply remove commas.
    	 * 
    	 * In this version, we'll perform a sanity check, first.
    	 * 
    	 * The conversion will detect multiple decimal points.
    	 * We insist on a decimal place.
    	 * If we see a comma, it must not be after the decimal place.
    	 */
    	if(FieldHelper.isNotEmpty(stringBigDecimal) &&
    	   stringBigDecimal.indexOf('.') > -1 &&
    	   stringBigDecimal.lastIndexOf(',') > stringBigDecimal.indexOf('.')) {
    		if(verbose) System.err.println("FieldHelper.parseBigDecimalSafe: unparseable BigDecimal: " + stringBigDecimal);
    		return null;
    	}
    	
    	try {
    		return new java.math.BigDecimal(stringBigDecimal.replaceAll(",", ""));
    	}
    	catch (Exception e) {
    		if(verbose) System.err.println("FieldHelper.parseBigDecimalSafe: unparseable BigDecimal: " + stringBigDecimal);
    		return null;
    	}
    }
    
    /**
     * 
     * @param stringBigDecimal
     * @return
     */
    public static java.math.BigDecimal parseBigDecimalSafe(String stringBigDecimal) {
    	return parseBigDecimalSafe(stringBigDecimal, false);
    }

    /**
     * 
     * @param stringCurrency
     * @param verbose
     * @return
     */
    public static java.math.BigDecimal parseCurrencySafe(String stringCurrency, Boolean verbose) {
    	if(isEmpty(stringCurrency)) return null;
    	else {
    		try {
    			return parseBigDecimalSafe(stringCurrency.replaceAll("[^A-Za-z0-9\\.\\-]", ""), verbose);
    		}
    		catch (Exception e) {
    			if(verbose) System.err.println("FieldHelper.parseCurrencySafe: unparseable BigDecimal: " + stringCurrency);
    			return null;
    		}
    	}
    }

    /**
     * 
     * @param stringCurrency
     * @return
     */
    public static java.math.BigDecimal parseCurrencySafe(String stringCurrency) {
    	return parseCurrencySafe(stringCurrency, false);
    }
    
    public static String makeKey(String value) {
    	if(isEmpty(value)) return null;
    	else {
    		String newValue = value.toUpperCase().replaceAll("[^A-Z0-9]", "").trim();
        	if(isEmpty(newValue)) return null;
        	else return newValue;
    	}
    }
    
    /**
     * 1.7.1
     * 
     * @param stringXML
     * @return
     */
    public static String encodeXML(String stringXML) {
    	if(FieldHelper.isEmpty(stringXML)) return null;
    	else return stringXML.replaceAll("&", "&amp;").replaceAll("<", "&lt;");
    }

    /**
     * 
     * @param field
     * @param position	Positioning starts at 1
     * @param regex
     * @return
     */
    public static String getFieldAtPosition(String field, int position, String regex) {
    	if(FieldHelper.isEmpty(field) ||
    	   position < 1) return null;

 	   if(regex == null) return null;

    	try {
    		return field.split(regex)[position - 1];
    	}
    	catch(Exception e) {
    		return null;
    	}
    }
    
    public static String getUUID() {
    	return UUID.randomUUID().toString();
    }
    
    public static String getMD5(String field) {
    	if(isEmpty(field)) return null;
    	
    	try {
    		java.security.MessageDigest md = java.security.MessageDigest.getInstance("MD5");
    		md.reset();
    		md.update(field.getBytes("UTF-8"));
    		byte[] digest = md.digest();
    		java.math.BigInteger bigInt = new java.math.BigInteger(1, digest);
    		String hashText = bigInt.toString(16);
    		// 	Now we need to zero pad it if you actually want the full 32 chars.
    		while(hashText.length() < 32 ){
    			hashText = "0" + hashText;
    		}
        	return hashText;
    	}
    	catch (Exception e) {
    		return null;
    	}
    }
 
    public static String getSHA256(String field) {
    	if(isEmpty(field)) return null;
    	
    	try {
    		java.security.MessageDigest md = java.security.MessageDigest.getInstance("SHA-256");
    		md.reset();
    		md.update(field.getBytes("UTF-8"));
    		byte[] digest = md.digest();
    		java.math.BigInteger bigInt = new java.math.BigInteger(1, digest);
    		String hashText = bigInt.toString(16);
    		// 	Now we need to zero pad it if you actually want the full 32 chars.
    		while(hashText.length() < 32 ){
    			hashText = "0" + hashText;
    		}
        	return hashText;
    	}
    	catch (Exception e) {
    		return null;
    	}
    }
    //public static String getSHA256(String field);
}