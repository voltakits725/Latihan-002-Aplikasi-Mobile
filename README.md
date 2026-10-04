# KASIR DENGAN DISKON

**RAFLY KURNIAWAN - 1124160165**

## BUSINESS RULE

- **BR-01:** Belanja minimal Rp100.000 mendapat diskon 10%.
- **BR-02:** Member mendapat tambahan diskon 5% jika BR-01 terpenuhi.
- **BR-03:** Total potongan maksimal Rp25.000.

## SOURCE CODE

```dart
double hitungPersenDiskon(double totalBelanja, bool member) {
  if (totalBelanja >= 100000) {
    return member ? 15 : 10;
  }

  return 0;
}

double hitungPotongan(double totalBelanja, double persenDiskon) {
  double potongan = totalBelanja * persenDiskon / 100;

  if (potongan > 25000) {
    return 25000;
  }

  return potongan;
}

double hitungTotalBayar(
    double totalBelanja, double potongan) {
  return totalBelanja - potongan;
}

void main() {
  double totalBelanja = 150000;
  bool member = true;

  double persenDiskon =
      hitungPersenDiskon(totalBelanja, member);

  double potongan =
      hitungPotongan(totalBelanja, persenDiskon);

  double totalBayar =
      hitungTotalBayar(totalBelanja, potongan);

  print("=== KASIR DENGAN DISKON ===");
  print("Total Belanja : Rp$totalBelanja");
  print("Member        : $member");
  print("Diskon        : $persenDiskon%");
  print("Potongan      : Rp$potongan");
  print("Total Bayar   : Rp$totalBayar");
}