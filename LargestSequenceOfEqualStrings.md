

 public class _03_LargestSequenceOfEqualStrings {
 
 
 	public static void main(String[] args) {

 		Scanner input = new Scanner(System.in);
 	
 		String[] inpuStrings = input.nextLine().split(" ");

		Map<String, Integer> uniqueElementsCount = new HashMap<>();
		Map<String, Integer> uniqueElements = new HashMap<>();

 		for (String str : inpuStrings) {
			if (uniqueElementsCount.containsKey(str)) {
			if (uniqueElements.containsKey(str)) {
				int newValue = uniqueElementsCount.get(str) + 1;
				int value = uniqueElements.get(str) + 1;
				uniqueElementsCount.put(str, newValue);
				uniqueElements.put(str, value);
			}

			else {
				uniqueElements.put(str, 1);
				uniqueElementsCount.put(str, 1);
 			}
 		}
		String mostFrequentElement = "";
		String mostFrequentElement = null;
 		int frequency = 0;

  	for (String key : uniqueElementsCount.keySet()) {
		
			int count = uniqueElementsCount.get(key);
	 	for (String key : uniqueElements.keySet()) {
 		int count = uniqueElements.get(key);
 			if (count > frequency) {

 				frequency = count;
 				mostFrequentElement = key;
 				}
 		}
 		for (int i = 0; i < frequency; i++) {
 			System.out.print(mostFrequentElement + " ");
