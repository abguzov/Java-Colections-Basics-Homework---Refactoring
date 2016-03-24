

 public class _03_LargestSequenceOfEqualStrings {
 
 
 	public static void main(String[] args) {
 	public static void main(String[] args) {
		

 		// Input
 		// Input
 		Scanner input = new Scanner(System.in);
 		Scanner input = new Scanner(System.in);
 		String[] inpuStrings = input.nextLine().split(" ");
 		String[] inpuStrings = input.nextLine().split(" ");
		

		Map<String, Integer> uniqueElementsCount = new HashMap<>();
		Map<String, Integer> uniqueElements = new HashMap<>();
		

 		// Main Logic
 		// Main Logic
		// Adding each string into the HashMap and counting how many times it appears in the sequence
		// Adding each string into the HashMap and counting how many times it
		// appears in the sequence
 		for (String str : inpuStrings) {
 		for (String str : inpuStrings) {
			if (uniqueElementsCount.containsKey(str)) {
			if (uniqueElements.containsKey(str)) {
				int newValue = uniqueElementsCount.get(str) + 1;
				int value = uniqueElements.get(str) + 1;
				uniqueElementsCount.put(str, newValue);
				uniqueElements.put(str, value);
			}
			} else {
			else {
				uniqueElements.put(str, 1);
				uniqueElementsCount.put(str, 1);
 			}
 			}
 		}
 		}
		

 		// Finding the longest sequence of equal strings
 		// Finding the longest sequence of equal strings
		String mostFrequentElement = "";
		String mostFrequentElement = null;
 		int frequency = 0;
 		int frequency = 0;
  	for (String key : uniqueElementsCount.keySet()) {
		
			int count = uniqueElementsCount.get(key);
	 	for (String key : uniqueElements.keySet()) {
 		int count = uniqueElements.get(key);
 			if (count > frequency) {
 			if (count > frequency) {
 				frequency = count;
 				frequency = count;
 				mostFrequentElement = key;
 				mostFrequentElement = key;
 			}
 			}
 		}
 		}

 		// Output
 		// Output
 		for (int i = 0; i < frequency; i++) {
 		for (int i = 0; i < frequency; i++) {
 			System.out.print(mostFrequentElement + " ");
