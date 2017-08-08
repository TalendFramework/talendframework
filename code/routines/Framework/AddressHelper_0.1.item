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
public class AddressHelper {
	
	/**
	 * Constructs a single address address from a number of lines
	 * 
	 * @param line1
	 * @param line2
	 * @param line3
	 * @param line4
	 * @param separator
	 * @return
	 */
	public static String makeAddressFrom4(String line1, String line2, String line3, String line4, String separator) {
		String address = null;
		if(FieldHelper.isNotEmpty(line1)) address = line1.trim();
		if(FieldHelper.isNotEmpty(line2)) {
			if(address != null) {
				
				// Does it appear that we only have a street number, so far? If so, we'll always use ' ' as the separator.
				if(address.matches("\\d+(?i)[a-z]")) address = String.format("%s%s%s", address, " ", line2.trim());
				else address = String.format("%s%s%s", address, separator, line2.trim());
			}
			else address = line2.trim();
		}
		if(FieldHelper.isNotEmpty(line3)) {
			if(address != null) {
				
				// Does it appear that we only have a street number, so far? If so, we'll always use ' ' as the separator.
				if(address.matches("\\d+(?i)[a-z]")) address = String.format("%s%s%s", address, " ", line3.trim());
				else address = String.format("%s%s%s", address, separator, line3.trim());
			}
			else address = line3.trim();
		}
		if(FieldHelper.isNotEmpty(line4)) {
			if(address != null) {
				
				// Does it appear that we only have a street number, so far? If so, we'll always use ' ' as the separator.
				if(address.matches("\\d+(?i)[a-z]")) address = String.format("%s%s%s", address, " ", line4.trim());
				else address = String.format("%s%s%s", address, separator, line4.trim());
			}
			else address = line3.trim();
		}
		
		return address;
	}

	public static String makeAddressFrom3(String line1, String line2, String line3, String separator) {
		return makeAddressFrom4(line1, line2, line3, null, separator);
	}
	
	public static String makeAddressFrom2(String line1, String line2, String separator) {
		return makeAddressFrom4(line1, line2, null, null, separator);
	}	
	
	public static String makeAddressFrom4(String line1, String line2, String line3, String line4) {
		return makeAddressFrom4(line1, line2, line3, line4, "\n");
	}
	
	public static String makeAddressFrom3(String line1, String line2, String line3) {
		return makeAddressFrom4(line1, line2, line3, null, "\n");
	}

	public static String makeAddressFrom2(String line1, String line2) {
		return makeAddressFrom4(line1, line2, null, null, "\n");
	}	
}
