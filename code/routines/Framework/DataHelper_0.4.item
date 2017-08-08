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
public class DataHelper {
	
    static Integer rowsToGenerate_ = null;

		/**
		 * defines the data quality level to be returned.
		 * 
		 * 0=best
		 * 1=add null values
		 * 2=add bad values
		 */
		static int qualityLevel = 1;
		static int qualityStandard = 1000; // 1 in 1000 items will be poor quality

	/*
	 * Data Generation Routines.
	 */
	    static java.util.Random random = new java.util.Random();
	    
		static String dateFormat_ = "dd-MMM-yyyy";

	    
	    public static int genderMale = 0;
	    public static int genderFemail = 1;
	    
	    static String maleGender[] = { "Male" };

	    static String femaleGender[] = { "Female" };
	    
	    static String maleTitle[] = { "Mr", "Mr", "Mr", "Mr", "Mr", "Mr", "Mr", "Mr", "Mr", "Mr",
	    							  "Dr" };
	    
	    static String femaleTitle[] = { "Mrs", "Mrs", "Mrs", "Mrs", "Mrs", "Mrs", "Mrs", "Mrs", "Mrs", "Mrs",
	    							    "Miss", "Miss", "Miss", "Miss", "Miss", "Miss", "Miss", "Miss", "Miss", "Miss", 
	    							    "Dr", "Ms", "Ms", "Ms", "Ms", "Ms", "Ms", "Ms", "Ms", "Ms", "Ms" };
	    
	    static String salutation[] = {"Formal", "Informal" };
	    
	    static String maleName[] = { "Harry", "Jack", "Oliver", "Charlie", "James", "George", "Thomas", "Ethan", "Jacob", "William", 
	    							 "Daniel", "Joshua", "Max", "Noah", "Alfie", "Samuel", "Dylan", "Oscar", "Lucas", "Aidan",
	    							 "Isaac", "Riley", "Henry", "Benjamin", "Joseph", "Alexander", "Lewis", "Leo", "Tyler", "Jayden",
	    							 "Zac", "Freddie", "Archie", "Logan", "Adam", "Ryan", "Nathan", "Matthew", "Sebastian", "Jake",
	    							 "Toby", "Alex", "Luke", "Liam", "Harrison", "David", "Jamie", "Edward", "Luca", "Elliot",
	    							 "Aaron", "Finley", "Michael", "Zachary", "Mason", "Sam", "Muhammad", "Connor", "Ben", "Reuben",
	    							 "Theo", "Ryhs", "Arthur", "Caleb", "Dexter", "Rory", "Jenson", "Evan", "Gabriel", "Ewan",
	    							 "Callum", "Seth", "Felix", "Austin", "Owen", "Leon", "Cameron", "Jude", "Harley", "Blake",
	    							 "Harvey", "Tom", "Hugo", "Finn", "Bobby", "Hayden", "Kyle", "Jasper", "Tommy", "Eli",
	    							 "Kian", "Andrew", "John", "Louie", "Dominic", "Joe", "Elijan", "Kai", "Frankie", "Stanley" };
	    
	    static String femaleName[] = { "Amelia", "Lily", "Emily", "Sophia", "Isabelle", "Sophie", "Olivia", "Jessica", "Chloe", "Mia", 
	    							   "Isla", "Isabella", "Ava", "Charlotte", "Grace", "Evie", "Poppy", "Lucy", "Ella", "Holly",
	    							   "Emma", "Molly", "Annabelle", "Erin", "Freya", "Ruby", "Scarlett", "Alice", "Layla", "Hannah",
	    							   "Eva", "Imogen", "Millie", "Daisy", "Abigail", "Amy", "Zoe", "Megan", "Maisie", "Phoebe",
	    							   "Maya", "Anna", "Eliza", "Caitlin", "Amelie", "Jasmine", "Florence", "Sienna", "Madison", "Eleanor",
	    							   "Darcey", "Lola", "Elizabeth", "Leah", "Matilda", "Summer", "Elsie", "Ellie", "Zara", "Rosie",
	    							   "Kayla", "Esme", "Amber", "Georgia", "Bethany", "Rose", "Evelyn", "Lexi", "Niamh", "Katie",
	    							   "Alyssa", "Lauren", "Heidi", "Gracie", "Skye", "Willow", "Faith", "Beth", "Alexandra", "Iris",
	    							   "Harriet", "Violet", "Lara", "Martha", "Rebecca", "Seren", "Gabriella", "Tilly", "Naomi", "Sarah",
	    							   "Clara", "Nicole", "Elise", "Mila", "Annie", "Sara", "Bella", "Francesca", "Elena", "Libby" };
	    
	    static String lastName[] = {"Smith", "Jones", "Taylor", "Williams", "Brown", "Davies", "Evans", "Wilson", "Thomas", "Roberts",
			"Johnson", "Lewis", "Walker", "Robinson", "Wood", "Thompson", "White", "Watson", "Jackson", "Wright",
			"Green", "Harris", "Cooper", "King", "Lee", "Martin", "Clarke", "James", "Morgan", "Hughes",
			"Edwards", "Hill", "Moore", "Clark", "Harrison", "Scott", "Young", "Morris", "Hall", "Ward",
			"Turner", "Carter", "Phillips", "Mitchell", "Patel", "Adams", "Campbell", "Anderson", "Allen", "Cook",
			"Bailey", "Parker", "Miller", "Davis", "Murphy", "Price", "Bell", "Baker", "Griffiths", "Kelly",
			"Simpson", "Marshall", "Collins", "Bennett", "Cox", "Richardson", "Fox", "Gray", "Rose", "Chapman",
			"Hunt", "Robertson", "Shaw", "Reynolds", "Lloyd", "Ellis", "Richards", "Russell", "Wilkinson", "Khan",
			"Graham", "Stewart", "Reid", "Murray", "Powell", "Palmer", "Holmes", "Rogers", "Stevens", "Walsh",
			"Hunter", "Thomson", "Matthews", "Ross", "Owen", "Mason", "Knight", "Kennedy", "Butler", "Saunders",
			"Cole", "Pearce", "Dean", "Foster", "Harvey", "Hudson", "Gibson", "Mills", "Berry", "Barnes",
			"Pearson", "Kaur", "Booth", "Dixon", "Grant", "Gordon", "Lane", "Harper", "Ali", "Hart",
			"Mcdonald", "Brooks", "Ryan", "Carr", "Macdonald", "Hamilton", "Johnston", "West", "Gill", "Dawson",
			"Armstrong", "Gardner", "Stone", "Andrews", "Williamson", "Barker", "George", "Fisher", "Cunningham", "Watts",
			"Webb", "Lawrence", "Bradley", "Jenkins", "Wells", "Chambers", "Spencer", "Poole", "Atkinson", "Lawson",
			"Day", "Woods", "Rees", "Fraser", "Black", "Fletcher", "Hussain", "Willis", "Marsh", "Ahmed",
			"Doyle", "Lowe", "Burns", "Hopkins", "Nicholson", "Parry", "Newman", "Jordan", "Henderson", "Howard",
			"Barrett", "Burton", "Riley", "Porter", "Byrne", "Houghton", "John", "Perry", "Baxter", "Ball",
			"Mccarthy", "Elliott", "Burke", "Gallagher", "Duncan", "Cooke", "Austin", "Read", "Wallace", "Hawkins",
			"Hayes", "Francis", "Sutton", "Davidson", "Sharp", "Holland", "Moss", "May", "Bates", "Morrison",
			"Bob", "Oliver", "Kemp", "Page", "Arnold", "Shah", "Stevenson", "Ford", "Potter", "Flynn",
			"Warren", "Kent", "Alexander", "Field", "Freeman", "Begum", "Rhodes", "Middleton", "Payne", "Stephenson",
			"PritchaGrd", "Gregory", "Bond", "Webster", "Dunn", "Donnelly", "Lucas", "Long", "Jarvis", "Cross",
			"Stephens", "Reed", "Coleman", "Nicholls", "Bull", "Bartlett", "Beattie", "Curtis", "Bird", "Patterson",
			"Tucker", "Bryant", "Lynch", "Mackenzie", "Ferguson", "Cameron", "Lopez", "Haynes", "Bolton", "Hardy",
			"Heath", "Davey", "Rice", "Jacobs", "Parsons", "Ashton", "Robson", "French", "Farrell", "Walton",
			"Gilbert", "Mcintyre", "Newton", "Norman", "Higgins", "Hodgson", "Sutherland", "Kay", "Bishop", "Burgess",
			"Simmons", "Hutchinson", "Moran", "Frost", "Sharma", "Slater", "Greenwood", "Kirk", "Fernandez", "Garcia" };
	    
	    static String emailHost[] = { "tbemailserver" };
	    
	    static String tld[] = { "com", "com", "com", "com", "com", "com", "com", "com", "com", "com",
	    						"co.uk", "co.uk", "co.uk", "co.uk", "co.uk",
	    						"net", "org", "eu" };

	    static String password[] = { "123456", "password", "12345678", "qwerty", "abc123", "123456789", "111111", "1234567", "iloveyou", "adobe123", 
	    							 "123123", "admin", "1234567890", "letmein", "photoshop", "1234", "monkey", "shadow", "sunshine", "12345", 
	    							 "password1", "princess", "azerty", "trustno1", "0" };
	    
	    static String phoneAreaCode[] = { "01400", "01403", "01404", "01405", "01406", "01407", "01408", "01409", "0141", "01420", 
	    								  "01422", "01423", "01424", "01425", "01427", "01428", "01429", "01430", "01431", "01432",
	    								  "01433", "01434", "01435", "01436", "01437", "01438", "01439", "01440", "01442", "01443",
	    								  "01444", "01445", "01446", "01449", "01450", "01451", "01452", "01453", "01454", "01455",
	    								  "01456", "01457", "01458", "01460", "01461", "01462", "01463", "01464", "01465", "01466",
	    								  "01467", "01469", "01470", "01471", "01472", "01473", "01474", "01475", "01476", "01477",
	    								  "01478", "01479", "01480", "01481", "01482", "01483", "01484", "01485", "01487", "01488",
	    								  "01489", "01490", "01491", "01492", "01493", "01494", "01495", "01496", "01497", "01499",
	    								  "01501", "01502", "01503", "01505", "01506", "01507", "01508", "01509", "0151", "01520",
	    								  "01522", "01524", "015242", "01525", "01526", "01527", "01528", "01529", "01530", "01531",
	    								  "01534", "01535", "01536", "01538", "01539", "015394", "015395", "015396", "01540", "01542",
	    								  "01543", "01544", "01545", "01546", "01547", "01548", "01549", "01550", "01553", "01554",
	    								  "01555", "01556", "01557", "01558", "01559", "01560", "01561", "01562", "01563", "01564",
	    								  "01565", "01566", "01567", "01568", "01569", "01570", "01571", "01572", "01573", "01575",
	    								  "01576", "01577", "01578", "01579", "01580", "01581", "01582", "01583", "01584", "01586",
	    								  "01588", "01590", "01591", "01592", "01593", "01594", "01595", "01597", "01598", "01599" };

	    static String country[] = { "United Kingdom", "USA", "France", "Germany", "Italy", "Spain" };

	    
	    //{ "United Kingdom", "UK", "England", "U.K.", "Britain", "Great Britain", "GB", "G.B.", "Scotland", "Wales", "Northern Ireland" } };


		static String buildingNumber[] = {  "1", "1", "1", "1", "1", "1", "1", "1", "1", "1",
			 "1", "1", "1", "1", "1", "1", "1", "1", "1", "1",
			 "2", "2", "2", "2", "2", "2", "2", "2", "2", "2",
			 "2", "2", "2", "2", "2", "2", "2", "2", "2", "2",
			 "3", "3", "3", "3", "3", "3", "3", "3", "3", "3",
			 "3", "3", "3", "3", "3", "3", "3", "3", "3", "3",
			 "4", "4", "4", "4", "4", "4", "4", "4", "4", "4",
			 "4", "4", "4", "4", "4", "4", "4", "4", "4", "4",
			 "5", "5", "5", "5", "5", "5", "5", "5", "5", "5",
			 "5", "5", "5", "5", "5", "5", "5", "5", "5", "5",
			 "6", "6", "6", "6", "6", "6", "6", "6", "6", "6",
			 "6", "6", "6", "6", "6", "6", "6", "6", "6", "6",
			 "7", "7", "7", "7", "7", "7", "7", "7", "7", "7",
			 "7", "7", "7", "7", "7", "7", "7", "7", "7", "7",
			 "8", "8", "8", "8", "8", "8", "8", "8", "8", "8",
			 "8", "8", "8", "8", "8", "8", "8", "8", "8", "8",
			 "9", "9", "9", "9", "9", "9", "9", "9", "9", "9",
			 "9", "9", "9", "9", "9", "9", "9", "9", "9", "9",
			 "10", "10", "10", "10", "10", "10", "10", "10", "10", "10",
			 "10", "10", "10", "10", "10", "10", "10", "10", "10", "10",
			 "11", "11", "11", "11", "11", "11", "11", "11", "11", "11",
			 "11", "11", "11", "11", "11", "11", "11", "11", "11", "11",
			 "12", "12", "12", "12", "12", "12", "12", "12", "12", "12",
			 "12", "12", "12", "12", "12", "12", "12", "12", "12", "12",
			 "13", "13", "13", "13", "13", "13", "13", "13", "13", "13",
			 "13", "13", "13", "13", "13", "13", "13", "13", "13", "13",
			 "14", "14", "14", "14", "14", "14", "14", "14", "14", "14",
			 "14", "14", "14", "14", "14", "14", "14", "14", "14", "14",
			 "15", "15", "15", "15", "15", "15", "15", "15", "15", "15",
			 "15", "15", "15", "15", "15", "15", "15", "15", "15", "15",
			 "16", "16", "16", "16", "16", "16", "16", "16", "16", "16",
			 "1A", "1B", "2A", "2B", "3A", "3B", "4A", "4B", "5A", "5B",
			 "6A", "6B", "7A", "7B", "8A", "8B", "9A", "9B", "10A", "10B",   
			 "11A", "11B", "12A", "12B", "13A", "13B", "14A", "14B", "15A", "15B" };

		static String buildingName[] = { "Orchard House", "Meadow Cottage", "Rose Cottage", "Holly Cottage",
			 "Oak House", "Willow Cottage", "School House", "The Willows",
			 "Sunnyside", "Springfield", "Corner House", "Highfield",
			 "Old School House", "Primrose Cottage", "Mill House", "The Old Rectory",
			 "Yew Tree Cottage", "The Old Vicarage", "Oaklands", "The Old Post Office",
			 "Lilac Cottage", "Honeysuckle Cottage" };
		
static String streetName[] = { "Aire", "Avon", "Bann", "Barrow", "Blackwater", "Boyne", "Clyde", "Dee", "Don", "Eden", 
	   "Erne", "Great", "Lee", "Liffey", "Medway", "Mersey", "Nene", "Nore", "Ribble", "Severn",
	   "Shannon", "Spey", "Suir", "Tay", "Tees", "Teme", "Thames", "Trent", "Tweed", "Tyne",
	   "Albert", "Alexander", "Chester", "Church", "George", "Grange", "Green", "Grove", "High", "Highfield",
	   "King", "Kings", "Kingsway", "London", "Main", "Manchester", "Manor", "Mill", "New", "North",
	   "Park", "Queen", "Queens", "Richmond", "School", "South", "Springfield", "St. John's", "Stanley", "Station",
	   "Victoria", "West", "Windsor", "York", "Fuscia" };

static String streetType[] = { "Street", "Close", "Avenue", "Road", "Crescent", "Square", "Lane", "Way", "Place" };

static String town[] = { "Ampthill", "Arlesey", "Bedford", "Biggleswade", "Dunstable", 
"Flitwick", "Houghton Regis", "Kempston", "Leighton Buzzard", "Linslade",
"Luton", "Potton", "Sandy", "Shefford", "Stotfold",
"Wixams", "Woburn", "Ascot", "Bracknell", "Crowthorne",
"Earley", "Eton", "Hungerford", "Lambourn", "Maidenhead",
"Newbury", "Reading", "Sandhurst", "Slough", "Thatcham",
"Windsor", "Wokingham", "Woodley", "Bristol", "Amersham",
"Aylesbury", "Beaconsfield", "Bletchley", "Buckingham", "Chesham",
"Fenny Stratford", "High Wycombe", "Marlow", "Milton Keynes", "Newport Pagnell",
"Olney", "Princes Risborough", "Stony Stratford", "Wendover", "Winslow",
"Woburn Sands", "Wolverton and Greenleys", "Cambridge", "Chatteris", "Ely",
"Fulbourn", "Godmanchester", "Hanley Grange", "Huntingdon", "March",
"Northstowe", "Peterborough", "Ramsey", "Soham", "St Ives",
"St Neots", "Whittlesey", "Wisbech", "Alsager", "Birchwood",
"Bollington", "Chester", "Congleton", "Crewe", "Ellesmere Port",
"Frodsham", "Knutsford", "Macclesfield", "Malpas", "Middlewich",
"Nantwich", "Neston", "Northwich", "Poynton with Worth", "Runcorn",
"Sandbach", "Warrington", "Widnes", "Wilmslow", "Winsford",
"Bodmin", "Bude", "Callington", "Camborne", "Camelford",
"Charlestown", "Falmouth", "Fowey", "Hayle", "Helston" };

	//static String region[][] = { { "United Kingom", "USA", "France", "Germany", "Italy", "Spain" }, { "Bedfordshire", "Berkshire", "Bristol", "Buckinghamshire", "Cambridgeshire", 
	static String region[] = { "Bedfordshire", "Berkshire", "Bristol", "Buckinghamshire", "Cambridgeshire", 
  "Cheshire", "Cornwall", "Cumbria", "Derbyshire", "Devon",
  "Dorset", "Durham", "East Riding of Yorkshire", "East Sussex", "Essex",
  "Gloucestershire", "Hampshire", "Hereford and Worcester", "Hertfordshire", "Isle of Man",
  "Isle of Wight", "Kent", "Lancashire", "Leicestershire", "Lincolnshire",
  "London", "Manchester", "Merseyside", "Middlesex", "Norfolk",
  "North Yorkshire", "Northamptonshire", "Northumberland", "Nottinghamshire", "Oxfordshire",
  "Rutland", "Shropshire", "Somerset", "South Yorkshire", "Staffordshire",
  "Suffolk", "Surrey", "Tyne and Wear", "Warwickshire", "West Midlands",
  "West Sussex", "West Yorkshire", "Wiltshire", "County Antrim", "County Armagh",
  "County Down", "County Fermanagh", "County Londonderry", "County Tyrone", "Aberdeenshire",
  "Angus", "Argyll and Bute", "Ayrshire", "Clackmannanshire", "Dumfries and Galloway",
  "Dunbartonshire", "Dundee", "East Lothian", "Edinburgh", "Fife",
  "Glasgow", "Highland", "Lanarkshire", "Midlothian", "Moray",
  "Orkney", "Perth and Kinross", "Renfrewshire", "Scottish Borders", "Shetland Isles",
  "Stirling", "West Lothian", "Western Isles", "Anglesey/Sir Fon", "Blaenau Gwent",
  "Caerphilly", "Cardiff", "Carmarthenshire", "Ceredigion", "Conwy",
  "Denbighshire", "Flintshire", "Glamorgan", "Gwynedd", "Merthyr Tydfil",
  "Monmouthshire", "Neath Port Talbot", "Newport", "Pembrokeshire", "Powys" };
  //"Monmouthshire", "Neath Port Talbot", "Newport", "Pembrokeshire", "Powys" }, { "California" }, { "" }, { "" }, { "" }, { "" }};

static String junk[] = { "Mr", "Mrs", "Mr", "Mrs", "Mr", "Mrs", "Mr", "Mrs",
						 "James", "Bob", "Steve", "Mary", "Kate", "Sarah",
						 "Smith", "Robertson", "Jones", "Smith", "Robertson", "Jones",
						 "London", "Oxford","London", "Oxford","London", "Oxford","London", "Oxford",
						 "Dog", "Cat", "Lemon", "Orange", "Dog", "Cat", "Lemon", "Orange",
						 "Street", "Avenue", "UK", "United Kingsom", "USA", "USA",
						 "Unavailable", "Please call back", "Gone away", "Will ring back", "Do not contact",
						 "Managing Director", "CEO", "Salesman", "Head of Marketing",
						 "Revenue", "Invoice", "Order",
						 "qw", "we", "fhvjsdd", "rtyjhkltlf",
						 "#", ":", ";", "|", ",", "/", "\\", "\n", "\t", "\"", "'",
					     "1", "2.2", "-2.3", "200-", "1,000", "1.1.1", "-1.2.1", "£100", "£300-", "-£200", "$100", "-$200", "$300-",
					     "1-Sep-1752", "01/01/1970", "31-12-2015", "1-Jul-2048", "30-02-2015" };
				     
static String junkNumbers[] = { "1", "2", "6", "9",
					     		"100", "200", "3000", "4000", "10000", "20000", "300000", "4000000", "50000000", "6000000000",
					     		"1.1", "2.2", "3.333", "4.444", "5.5555", "10.0000001",
					     		"-1", "-2.2", "-2.3", "-2.6", "-2.54", "-10.001221",
					     		"100-", "200.20-",
					     		"1,000", "2,000,000.10", "-1,000", "-1,000.3",
					     		"1.1.1", "-1.2.1", "£100", "-£200", "£300-", "$200", "$300", "$300.12", "-$100", "$100-" };

static String junkDates[] = { "1-Sep-1752", "01/09/1752", "01-09-1752",
					     	  "1-Jan-1970", "01/01/1970", "01-09-1970",
					     	  "31-Dec-2015", "31/12/2015", "31-12-2015",
					     	  "1-Jul-2048", "01/07/2048", "01/07/2048",
					     	  "30-Feb-2015", "30/02/2015", "30/02/2015" };

/**
 * 
 */
public static void setRowsToGenerate(Integer rowsToGenerate) {
	rowsToGenerate_ = rowsToGenerate;
}

/**
 * 
 * @return
 */
public static Integer getRowsToGenerate() {
	return rowsToGenerate_;
}

/**
 * 
 */
public static void setDateFormat(String dateFormat) {
	if(FieldHelper.isNotEmpty(dateFormat)) dateFormat_ = dateFormat;
}

/**
 * 
 * @return
 */
public static String getDateFormat() {
	return dateFormat_;
}



/**
 * Returns an integer between 0..max
 * 
 * @param max
 * @return
 */
public static int getRandom(int max) { return random.nextInt(max + 1); }

	public static void setQualityLevel(int newQualityLevel) { qualityLevel = newQualityLevel; }
	public static int getQualityLevel() { return qualityLevel; }
	
	public static void setQualityStandard(int newQualityStandard) { qualityStandard = newQualityStandard; }
	public static int getQualityStandard() { return qualityStandard; }
	
	public static int getLookupIndex() { if(getQualityLevel() < 2) return 0; else return getQualityLevel() - 1; }

	
	public static boolean returnPoorQuality() {
		if(getQualityLevel() == 1 || getQualityLevel() == 2) {
			if(getRandom(getQualityStandard()) == 0) return true;
			else return false;
		}
		else return false;
	}
	
	public static String getPoorQuality() {
		if(getQualityLevel() == 1) return null;
		else {
			if(getRandom(5) == 0) return junk[random.nextInt(junk.length)];
			else return null;
		}
	}

/**
 * Returns an integer between min..max
 * 
 * @param min
 * @param max
 * @return
 */
public static int getRandom(int min, int max) {
	return random.nextInt(max) + min;
}

	/*
	 * PERSON.
	 */

	/**
	 * Returns Gender, Male or Female.
	 * 
	 * @return
	 */
	public static int makeGender() {
		return random.nextInt(2);
	}
	
	/**
	 * Returns Male Gender Name.
	 * 
	 * @return
	 */
	public static String makeGenderNameMale() {
		if(returnPoorQuality()) return getPoorQuality();
		else return maleGender[random.nextInt(maleGender.length)];
	}

	/**
	 * Returns Female Gender Name.
	 * 
	 * @return
	 */
	public static String makeGenderNameFemale() {
		if(returnPoorQuality()) return getPoorQuality();
		else return femaleGender[random.nextInt(femaleGender.length)];
	}
	
	/**
	 * 
	 * @param gender
	 * @return
	 */
	public static String makeGenderName(int gender) {
		if(gender == 0) return makeGenderNameMale();
		else if(gender == 1) return makeGenderNameFemale();
		else return null;
	}

	/**
	 * Returns Male Title.
	 * 
	 * @return
	 */
	public static String makeTitleMale() {
		if(returnPoorQuality()) return getPoorQuality();
		else return maleTitle[random.nextInt(maleTitle.length)];
	}

	/**
	 * Returns Female Title.
	 * 
	 * @return
	 */
	public static String makeTitleFemale() {
		if(returnPoorQuality()) return getPoorQuality();
		else return femaleTitle[random.nextInt(femaleTitle.length)];
	}

	/**
	 * 
	 * @param gender
	 * @return
	 */
	public static String makeTitle(int gender) {
		if(gender == 0) return makeTitleMale();
		else if(gender == 1) return makeTitleFemale();
		else return null;
	}
	
	public static String makeFirstNameMale() {
		if(returnPoorQuality()) return getPoorQuality();
		else return maleName[random.nextInt(maleName.length)];
	}

	public static String makeFirstNameFemale() {
		if(returnPoorQuality()) return getPoorQuality();
		else return femaleName[random.nextInt(femaleName.length)];
	}

	/**
	 * 
	 * @param gender
	 * @return
	 */
	public static String makeFirstName(int gender) {
		if(gender == 0) return makeFirstNameMale();
		else if(gender == 1) return makeFirstNameFemale();
		else return null;
	}
	
	/**
	 * 
	 * @return
	 */
	public static String makeLastName() {
		if(returnPoorQuality()) return getPoorQuality();
		else return lastName[random.nextInt(lastName.length)];
	}

/*
 * ADDRESS
 */
	
	/**
	 * 
	 */
	public static Integer makeCountryId() {
		if(returnPoorQuality()) return null;
		else return random.nextInt(country.length);
	}
	
	public static String makeCountry(Integer countryId) {
		if(returnPoorQuality()) return getPoorQuality();
		else if(countryId != null && countryId >= 0) return country[countryId];
		else return country[random.nextInt(country.length)];
	}
	
	public static String makeCountry() {
		return makeCountry(null);
	}

	public static String makeRegion(Integer countryId) {
		if(returnPoorQuality()) return getPoorQuality();
		//else if(countryId != null && countryId >= 0) return region[0][random.nextInt(region[0].length)];
		//else return region[countryId][random.nextInt(region[countryId].length)];
		else return region[random.nextInt(region.length)];
	}
	
	public static String makeRegion() {
		return makeRegion(null);
	}

	
	
	public static String makeBuildingNumber() {
		if(returnPoorQuality()) return getPoorQuality();
		else return buildingNumber[random.nextInt(buildingNumber.length)];
	}

	public static String makeBuildingName() {
		if(returnPoorQuality()) return getPoorQuality();
		else return buildingName[random.nextInt(buildingName.length)];
	}
	
	public static String makeBuildingNameNumber() {
		if(random.nextInt(10) == 0) return makeBuildingName();
		else return makeBuildingNumber();
	}
	
	public static String makeStreetName() {
		if(returnPoorQuality()) return getPoorQuality();
		else return String.format("%s %s",
							 streetName[random.nextInt(streetName.length)],
							 streetType[random.nextInt(streetType.length)]);
	}
	
	public static String makeTown() {
		if(returnPoorQuality()) return getPoorQuality();
		else return town[random.nextInt(town.length)];
	}

	public static String makeCity() {
		return makeTown();
	}
	
	
	/**
	 * 
	 * @return
	 * @deprecated
	 */
	public static String makeCounty() {
		return makeRegion();
	}
	
	public static String makePostalCode(String county) {
		if(returnPoorQuality()) return getPoorQuality();
		else if(FieldHelper.isEmpty(county)) return null;
		else if(county.length() < 2) return "XX10 1AB";
		else return String.format("%s%d %d%s%s",
								  county.substring(0, 2).toUpperCase(),
								  DataHelper.getRandom(1, 11),
								  DataHelper.getRandom(0, 9),
								  county.substring(1, 2).toUpperCase(),
								  county.substring(0, 1).toUpperCase());
	}
	

	public static String makeState() {
		return makeCounty();
	}

	public static String makeStreetLine1() {
		String buildingNameNumber = makeBuildingNameNumber();
		String streetName = makeStreetName();
		
		if(FieldHelper.isEmpty(buildingNameNumber)) return streetName;
		else if(FieldHelper.isEmpty(streetName)) return buildingNameNumber;
		else {
			if(! buildingNameNumber.substring(0, 1).matches("[0-9]")) buildingNameNumber = String.format("%s, ", buildingNameNumber);
			return String.format("%s %s", buildingNameNumber, streetName);
		}
	}
	
	/*
	 * COMMUNICATIONS
	 */
	
	public static String makeTLD() {
		if(returnPoorQuality()) return getPoorQuality();
		else return tld[random.nextInt(tld.length)];
	}

	public static String makePhoneNumber() {
		if(returnPoorQuality()) return getPoorQuality();
		else return String.format("0%d %d", getRandom(1231, 1881), getRandom(123456, 654321));
	}
	
	public static String makeMobilePhoneNumber() {
		if(returnPoorQuality()) return getPoorQuality();
		else return String.format("0%d 0%d", getRandom(7760, 7789), getRandom(23456, 54321));
	}
	
	public static String makeWebsite(String name) {
		if(returnPoorQuality()) return getPoorQuality();
		else return String.format("http://www.%s_ws.com", FileHelper.makeFileName(name)); 
	}
	
	/**
	 * 
	 * @param firstName
	 * @param lastName
	 * @param companyName
	 * @return
	 */
	public static String makeEmailAddress(String firstName, String lastName, String companyName) {
		if(returnPoorQuality()) return getPoorQuality();
		else {
			
			String lTld = String.format("%s.%s",
										FieldHelper.isNotEmpty(companyName) ? companyName : "emailacme",
										makeTLD());
			
			if(FieldHelper.isEmpty(firstName)) {
				if(FieldHelper.isEmpty(lastName)) return null;
				else return String.format("%s@%s", lastName, lTld);
			}
			else {
				if(FieldHelper.isEmpty(lastName)) return String.format("%s@%s", firstName, lTld);
				else return String.format("%s.%s@%s", firstName, lastName, lTld);
			}
		}
	}

	public static String makeEmailAddress(String firstName, String lastName) {
		return makeEmailAddress(firstName, lastName, null);
	}
	
	/**
	 * 
	 * @param emailAddress
	 * @return
	 */
	public static String obfuscateEmailAddress(String emailAddress) {
		if(FieldHelper.isEmpty(emailAddress)) return null;
		else {
			String[] element = emailAddress.split("@");
			if(element.length != 2) return emailAddress;
			else {
				String name = null;
				if(FieldHelper.isNotEmpty(element[0])) {
					if(element[0].length() > 2) name = String.format("x%s%s%sx", element[0].charAt(1), element[0].charAt(0), element[0].substring(2));
					else name = String.format("x%sx", element[0]);
				}
				
				String domain = null;
				if(FieldHelper.isNotEmpty(element[1])) {
					if(element[1].length() > 2) domain = String.format("x%s%s%s", element[1].charAt(1), element[1].charAt(0), element[1].substring(2));
					else domain = String.format("x%s", element[1]);
				}

				if(name == null || domain == null) return emailAddress;
				else return String.format("%s@%s", name, domain);
			}
		}
	}
}