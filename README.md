

BMI Calculator Functionality in Dart

double calculateBMI(double weightKg, double heightCm) {
  if (heightCm <= 0 || weightKg <= 0) {
    throw ArgumentError("Height and weight must be positive numbers.");
  }

  double heightM = heightCm / 100;
  double bmi = weightKg / (heightM * heightM);
  return double.parse(bmi.toStringAsFixed(2)); // rounds to 2 decimal places
}

String getBMICategory(double bmi) {
  if (bmi < 18.5) {
    return "Underweight";
  } else if (bmi < 24.9) {
    return "Normal weight";
  } else if (bmi < 29.9) {
    return "Overweight";
  } else {
    return "Obese";
  }
}

Example Usage

void main() {
  double weight = 70; // in kg
  double height = 175; // in cm

  try {
    double bmi = calculateBMI(weight, height);
    String category = getBMICategory(bmi);
    print("Your BMI is $bmi ($category)");
  } catch (e) {
    print("Error: ${e.toString()}");
  }
}

This includes input validation, BMI calculation, category classification, and rounded output.

Would you like this integrated into a Flutter UI or adapted for another language?
