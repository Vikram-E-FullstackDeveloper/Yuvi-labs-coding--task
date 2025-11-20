# Yuvi-labs-coding--task
import java.util.*;

class Main {
    public static void main(String args[]) {
        Scanner scanner = new Scanner(System.in);
        Random randomGen = new Random();
        int foundCount = 0;

        System.out.println("Enter array size(for N*N matrix): ");
        int size = scanner.nextInt();

        int[][] matrix = new int[size][size];

        for (int row = 0; row < size; row++) {
            for (int col = 0; col < size; col++) {
                matrix[row][col] = (randomGen.nextInt(10) + 1) * 2;
            }
        }

        System.out.println("Generated 2D array: ");

        System.out.print("    ");
        for (int col = 0; col < size; col++) {
            System.out.print("  0" + col + " ");
        }
        System.out.println();

        for (int row = 0; row < size; row++) {
            System.out.print("    ");
            for (int k = 0; k < size; k++) {
                System.out.print("+----");
            }
            System.out.print("+");
            System.out.println();

            System.out.print(" " + row + "0 | ");
            for (int col = 0; col < size; col++) {
                if (matrix[row][col] >= 10) {
                    System.out.print(matrix[row][col] + " | ");
                } else {
                    System.out.print(" " + matrix[row][col] + " | ");
                }
            }
            System.out.println();
        }

        System.out.print("    ");
        for (int k = 0; k < size; k++) {
            System.out.print("+----");
        }
        System.out.print("+");

        System.out.println("\nEnter a number to highlight (even 2-20): ");
        int target = scanner.nextInt();

        System.out.print("\n Array with " + target + " highlighted");
        System.out.println();

        System.out.print("    ");
        for (int col = 0; col < size; col++) {
            System.out.print("  0" + col + " ");
        }
        System.out.println();

        for (int row = 0; row < size; row++) {
            System.out.print("    ");
            for (int k = 0; k < size; k++) {
                System.out.print("+----");
            }
            System.out.print("+");
            System.out.println();

            System.out.print(" " + row + "0 |");
            for (int col = 0; col < size; col++) {

                if (matrix[row][col] >= 10) {
                    if (matrix[row][col] == target) {
                        System.out.print("[" + matrix[row][col] + "]|");
                        foundCount++;
                    } else {
                        System.out.print(" " + matrix[row][col] + " |");
                    }
                } else {

                    if (matrix[row][col] == target) {
                        System.out.print(" [" + matrix[row][col] + "]|");
                        foundCount++;
                    } else {
                        System.out.print("  " + matrix[row][col] + " |");
                    }
                }
            }
            System.out.println();
        }

        System.out.print("    ");
        for (int k = 0; k < size; k++) {
            System.out.print("+----");
        }
        System.out.print("+");

        System.out.print("\n\nNumber of " + target + " appeared " + foundCount + " time(s)");
    }
}
