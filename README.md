# Seven-Segment LED Display Control

This example demonstrates how to control a seven-segment LED display using an Arduino. The display cycles through the numbers 1 to 9 by setting the corresponding segments high or low.

## Code

```cpp
/* How to use a seven-segment LED display. */

byte pin[] = {2, 3, 4, 5, 6, 7, 8, 9};  // Arduino pin array

// Number array for displaying digits 1 to 9 on a 7-segment display
int number[9][8] = {
  {1, 1, 0, 0, 0, 1, 1, 1},  // 1
  {0, 0, 1, 0, 0, 0, 1, 0},  // 2
  {1, 0, 0, 0, 0, 0, 1, 0},  // 3
  {1, 1, 0, 0, 0, 1, 0, 0},  // 4
  {1, 0, 0, 0, 1, 0, 0, 0},  // 5
  {0, 0, 0, 0, 1, 0, 0, 0},  // 6
  {1, 1, 0, 0, 0, 0, 0, 1},  // 7
  {0, 0, 0, 0, 0, 0, 0, 0},  // 8
  {1, 1, 0, 0, 0, 0, 0, 0},  // 9
};

void setup() {
  // Initialize the 8 pins as OUTPUT
  for (byte a = 0; a < 8; a++) {
    pinMode(pin[a], OUTPUT);
  }
}

void loop() {
  // Display each number from 1 to 9
  for (int a = 0; a < 9; a++) {
    for (int b = 0; b < 8; b++) {
      digitalWrite(pin[b], number[a][b]);  // Set the segments
    }
    delay(500);  // Delay to allow each number to be displayed for 500ms
  }
}
