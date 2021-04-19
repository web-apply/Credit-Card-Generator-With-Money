# Credit Card Generator With Money
Hans Peter Luhn, a German with short history knowledge, was developed by our brother to check whether the numbers typed in 1954 were entered incorrectly. IMEI - Used as the verification code in the last character of numbers such as Credit card.

1. The number of characters entered must be 16.
2. A variable must be transferred to a variable with the sums of the double digits of the numbers with even indices.
3. The sums of the numbers with odd indices should be transferred to another variable.
4. Finally, we will check whether the sum of the two variables is divided by 10.


private bool generate(string pKartNo)
{
int toplam = 0;
for (int i = 0; i < 16; i++)
{
int sayi = Convert.ToInt32(pKartNo[i].ToString());

if (i % 2 == 0)
{
sayi = sayi * 2;
if (sayi.ToString().Length == 2)
sayi = Convert.ToInt32(sayi.ToString().Substring(0, 1)) + Convert.ToInt32(sayi.ToString().Substring(1, 1));
}

toplam += sayi;
}

if (toplam % 10 == 0)
return true;
else
return false;
}
