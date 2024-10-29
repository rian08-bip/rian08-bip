import java.util.Scanner;

public class KalkulatorSederhana {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String lanjut = "ya";

        while (lanjut.equalsIgnoreCase("ya")) {
            System.out.println("Pilihan operasi:");
            System.out.println("1. Penjumlahan");
            System.out.println("2. Pengurangan");
            System.out.println("3. Perkalian");
            System.out.println("4. Pembagian");
            System.out.print("Pilihan anda (1/2/3/4): ");
            int pilihan = scanner.nextInt();

            // Meminta input dua bilangan dari pengguna
            System.out.print("Masukkan bilangan 1: ");
            double bilangan1 = scanner.nextDouble();

            System.out.print("Masukkan bilangan 2: ");
            double bilangan2 = scanner.nextDouble();

            double hasil = 0;
            boolean operasiValid = true;

            // Menentukan operasi berdasarkan pilihan
            switch (pilihan) {
                case 1:
                    hasil = bilangan1 + bilangan2;
                    System.out.println("Operasi: Penjumlahan");
                    break;
                case 2:
                    hasil = bilangan1 - bilangan2;
                    System.out.println("Operasi: Pengurangan");
                    break;
                case 3:
                    hasil = bilangan1 * bilangan2;
                    System.out.println("Operasi: Perkalian");
                    break;
                case 4:
                    if (bilangan2 != 0) {
                        hasil = bilangan1 / bilangan2;
                        System.out.println("Operasi: Pembagian");
                    } else {
                        System.out.println("Kesalahan: Pembagian dengan nol tidak diperbolehkan.");
                        operasiValid = false;
                    }
                    break;
                default:
                    System.out.println("Pilihan tidak valid.");
                    operasiValid = false;
                    break;
            }

            // Menampilkan hasil jika operasi valid
            if (operasiValid) {
                System.out.println("Hasil: " + hasil);
            }

            // Menanyakan apakah ingin melanjutkan
            scanner.nextLine();  // Membersihkan buffer sebelum menerima input string
            System.out.print("Apakah ingin melanjutkan (ya/tidak)? ");
            lanjut = scanner.nextLine();
        }

        System.out.println("Terima kasih!");
        scanner.close();
    }
}
