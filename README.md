# indeksator
Indeksatorlar Standart massivlarda joylashgan alohida elementlarga murojaat qilish jarayoni ([]) 
orqali bajarilishi dasturchilarga yaxshi tanish. C # da indeksatorni belgilash orqali 
standart massiv singari indekslanishi mumkin bo'lgan maxsus sinflar va 
strukturalarni loyihalash mumkin. Ushbu alohida til vositasi maxsus turlarini 
(umumiy va umumiy bo'lmagan) yaratishda eng foydalidir. Indeksatorlar bir yoki 
ko'p o'lchovli bo'lishi mumkin. 
* Bir o'lchovli indeksatorning umumiy shakli: 
```Cs 
Murojaat_modifikatori element_turi this[int indeks] 
{ 
get  
{ 
// Indeks bilan aniqlangan qiymatni qaytarish. 
} 
set  
{ 
// Indeks bilan aniqlangan qiymatni o’rnatish. 
} 
}
```

va yana bir misolni taxlil qilaylik
```Cs
class Temperatura
{
    int[] t;
    public int Length;
    public Temperatura(int size)
    {
        t = new int[size];
        Length = size;
    }
    // indeksator e’lon qilish 
    public int this[int ind]
    {
        get
        {
            if (Math.Abs((double)ind) >= 0 & ind < Length) return t[ind];
            else return 1;
        }
        set
        {
            if ((int)Math.Abs((double)ind) < Length) t[ind] = value;
            else Console.WriteLine(ind + " indeksli elementga",
            "qiymat berishda chegaradan chiqildi");
        }
    }
}
 class Program
 {
     public static void Main()
     {
         Temperatura t1 = new Temperatura(4 * 10);
         
         for (int i1 = -13; i1 < 13; i1++) t1[i1] = i1 * i1;
         for (int i1 = 13; i1 < 15; i1++)
         {
             Console.WriteLine("t[{0}]={1}", i1, t1[i1]);
         }
     }
 }
```
 
 * Bu dasturda indeksator Tempetura classida joylashgan .Main metodida Temperator classi qayta yuklanib
 unga 40 qiymat berib yuborildi ,Temperator classida bu qiymatni massivning uzunligi sifatida qabul qiladi.
Misolda massiv elementlariga qiymat berayotganda 
berilgan diapazondan chiqilsa bu haqda ma’lumot beradi, massiv 
elementlariga murojaat qilayotganda berilgan diapozondagi mos 
indeksli qiymatni, diapozondan tashqari indeklarda 0 qiymatni 
qaytaradi. 
Dasturni ishga tushirsak, quyidagicha natija chiqadi
```Cs

