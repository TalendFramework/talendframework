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

public class QualityHelper {
	static java.math.BigDecimal oneHundred = new java.math.BigDecimal(100);

	/**
	 * 
	 * @param actual
	 * @param target
	 * @param percentageThreshold
	 * @param debug
	 * @return
	 */
	public static Boolean isThresholdMet(int actual, int target, java.math.BigDecimal percentageThreshold, boolean debug) {
		
		// 0.5 Resolve divide by zero errors, if no target specified
		if(target == 0) {
			if(debug) System.err.println(String.format("QualityHelper.isThresholdMet: target: zero: %d", target));
			return true;
		}
		
		else if(percentageThreshold == null ||
		
		   // 0.4 Allow threshold of 0
		   //percentageThreshold.compareTo(java.math.BigDecimal.ZERO) < 1 ||
		   percentageThreshold.compareTo(java.math.BigDecimal.ZERO) < 0 ||
		   percentageThreshold.compareTo(oneHundred) > 0) {
			if(debug) System.err.println(String.format("QualityHelper.isThresholdMet: percentageThreshold: invalid: %f", percentageThreshold));
			return false;
		}

		// This is absolute. We do not need to worry about minor rounding issues causing a return of true.
		else if(actual != target &&
			percentageThreshold.compareTo(oneHundred) == 0) {
			
			if(debug) System.err.println("QualityHelper.isThresholdMet: actual: " + actual +
					   " target: " + target +
					   " absoluteDiff: " + (actual - target) +
					   " percentageThreshold: " + percentageThreshold);
			
			return false;
		}
		// This is absolute.
		else if(actual == target &&
			percentageThreshold.compareTo(oneHundred) == 0) {
			
			if(debug) System.err.println("QualityHelper.isThresholdMet: actual: " + actual +
					   " target: " + target +
					   " absoluteDiff: " + (actual - target) +
					   " percentageThreshold: " + percentageThreshold +
					   " percentage reached: 100");
			
			return true;
		}
		else {
			java.math.BigDecimal percentageReached = new java.math.BigDecimal(actual).divide(new java.math.BigDecimal(target), 6, java.math.RoundingMode.HALF_DOWN).multiply(oneHundred);
			
			if(debug) System.err.println("QualityHelper.isThresholdMet: actual: " + actual +
							   " target: " + target +
							   " absoluteDiff: " + (actual - target) +
							   " percentageThreshold: " + percentageThreshold +
							   " percentageReached: " + percentageReached);

			/*
			System.err.println("actual: " + new java.math.BigDecimal(actual));
			System.err.println("target: " + new java.math.BigDecimal(target));
			System.err.println("actual/target: " + new java.math.BigDecimal(actual).divide(new java.math.BigDecimal(target), 6, java.math.RoundingMode.HALF_DOWN));
			*/

			if(percentageReached.compareTo(percentageThreshold) < 0) return false;
			else return true;
		}
	}
	
	/**
	 * 
	 * @param value
	 * @param target
	 * @param percentageThreshold
	 * @return
	 */
	public static Boolean isThresholdMet(int value, int target, java.math.BigDecimal percentageThreshold) {
		return isThresholdMet(value, target, percentageThreshold, false);
	}
}