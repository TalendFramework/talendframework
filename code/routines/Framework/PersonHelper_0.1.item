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
public class PersonHelper {
	
	/**
	 * Returns the first word. This is considered the first name.
	 * 
	 * @param name
	 * @return
	 */
	public static String getFirstName(String name) {
		if(FieldHelper.isEmpty(name)) return null;
		else {
			return name.split(" ")[0];
		}
	}

	/**
	 * Returns all but the last word. This is considered the first names.
	 * 
	 * @param name
	 * @return
	 */
	public static String getFirstNames(String name) {
		if(FieldHelper.isEmpty(name)) return null;
		else {
			return name.replaceAll(String.format(" %s$", name.split(" ")[name.split(" ").length - 1]), "").trim();
		}
	}

	/**
	 * Returns the last word. This is considered the last name. If there is only one word, then it is considered the first name.
	 * 
	 * @param name
	 * @return
	 */
	public static String getLastName(String name) {
		if(FieldHelper.isEmpty(name) || name.split(" ").length < 2) return null;
		else {
			return name.split(" ")[name.split(" ").length - 1];
		}
	}
}
