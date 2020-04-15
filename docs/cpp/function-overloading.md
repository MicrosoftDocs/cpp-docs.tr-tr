---
title: İşlev Aşırı Yüklemesi
ms.date: 03/27/2019
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
ms.openlocfilehash: a59c0e27a4500cb20ef42e9a55b4eb0004e07f65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368916"
---
# <a name="function-overloading"></a>İşlev Aşırı Yüklemesi

C++, aynı kapsamda aynı ada sahip birden fazla işlevin belirtilmesini sağlar. Bu işlevler *aşırı yüklü* işlevler olarak adlandırılır. Aşırı yüklenen işlevler, bağımsız değişken türlerine ve sayısına bağlı olarak bir işlev için farklı anlamsal sayılar sağlamanızı sağlar.

Örneğin, bir `print` bağımsız değişken `std::string` alan bir işlev, bir tür **çift**bağımsız değişkeni alan bir çok farklı görevler gerçekleştirebilir. Aşırı yükleme, sizi ' veya `print_string` `print_double`' gibi adlar kullanmak zorunda kalmaktan kurtarır. Derleme zamanında derleyici, arayanın geçtiği bağımsız değişken türüne bağlı olarak hangi aşırı yüklemenin kullanılacağını seçer.  Ararsanız, `print(42.0)` `void print(double d)` işlev çağrılır. `print("hello world")`Ararsanız, `void print(std::string)` aşırı yükleme çağrılır.

Hem üye hem de üye olmayan işlevleri aşırı yükleyebilirsiniz. Aşağıdaki tabloda, C++'nın aynı kapsamda aynı ana sahip işlev gruplarını birbirinden ayırmak için işlev bildiriminin hangi bölümlerini kullandığını gösterir.

### <a name="overloading-considerations"></a>Aşırı Yükleme Hakkında Önemli Noktalar

|İşlev Bildirimi Öğesi|Aşırı yükleme için kullanılır mı?|
|----------------------------------|---------------------------|
|İşlevin dönüş türü|Hayır|
|Bağımsız değişkenlerin sayısı|Evet|
|Bağımsız değişkenlerin türü|Evet|
|Elipsin varlığı veya yokluğu|Evet|
|**Typedef** adlarının kullanımı|Hayır|
|Belirtilmemiş dizi sınırları|Hayır|
|**const** veya **uçucu**|Evet, tüm fonksiyona uygulandığında|
|[Ref elemeleri](#ref-qualifiers)|Evet|

## <a name="example"></a>Örnek

Aşağıdaki örnekte, aşırı yüklemenin nasıl kullanılabileceği gösterilmektedir.

```cpp
// function_overloading.cpp
// compile with: /EHsc
#include <iostream>
#include <math.h>
#include <string>

// Prototype three print functions.
int print(std::string s);             // Print a string.
int print(double dvalue);            // Print a double.
int print(double dvalue, int prec);  // Print a double with a
                                     //  given precision.
using namespace std;
int main(int argc, char *argv[])
{
    const double d = 893094.2987;
    if (argc < 2)
    {
        // These calls to print invoke print( char *s ).
        print("This program requires one argument.");
        print("The argument specifies the number of");
        print("digits precision for the second number");
        print("printed.");
        exit(0);
    }

    // Invoke print( double dvalue ).
    print(d);

    // Invoke print( double dvalue, int prec ).
    print(d, atoi(argv[1]));
}

// Print a string.
int print(string s)
{
    cout << s << endl;
    return cout.good();
}

// Print a double in default precision.
int print(double dvalue)
{
    cout << dvalue << endl;
    return cout.good();
}

//  Print a double in specified precision.
//  Positive numbers for precision indicate how many digits
//  precision after the decimal point to show. Negative
//  numbers for precision indicate where to round the number
//  to the left of the decimal point.
int print(double dvalue, int prec)
{
    // Use table-lookup for rounding/truncation.
    static const double rgPow10[] = {
        10E-7, 10E-6, 10E-5, 10E-4, 10E-3, 10E-2, 10E-1,
        10E0, 10E1,  10E2,  10E3,  10E4, 10E5,  10E6 };
    const int iPowZero = 6;

    // If precision out of range, just print the number.
    if (prec < -6 || prec > 7)
    {
        return print(dvalue);
    }
    // Scale, truncate, then rescale.
    dvalue = floor(dvalue / rgPow10[iPowZero - prec]) *
        rgPow10[iPowZero - prec];
    cout << dvalue << endl;
    return cout.good();
}
```

Yukarıdaki kod dosya kapsamındaki `print` işlevinin aşırı yüklenmesini gösterir.

Varsayılan bağımsız değişken işlev türünün bir parçası olarak kabul edilir. Bu nedenle, aşırı yüklü işlevleri seçerken kullanılmaz. Yalnızca kendi varsayılan bağımsız değişkenlerinde farklı olan iki işlevde, aşırı yüklenmiş işlevler yerine birden çok tanım dikkate alınır.

Varsayılan bağımsız değişkenler aşırı yüklü işleçler için sağlanabilir.

## <a name="argument-matching"></a>Bağımsız Değişken Eşleştirme

İşlev çağrısında sağlanan bağımsız değişkenlerle geçerli kapsamdaki işlev bildirimlerinin en iyi eşleşmesi için aşırı yüklenen işlevler seçilir. Uygun bir işlev bulunursa, bu işlev çağrılır. Bu bağlamda "Uygun" ya anlamına gelir:

- Tam bir eşleşme bulundu.

- Önemsiz bir dönüştürme gerçekleştirildi.

- İntegral bir promosyon gerçekleştirildi.

- İstenilen bağımsız değişken türüne standart bir dönüştürme vardır.

- İstenilen bağımsız değişken türüne kullanıcı tanımlı dönüştürme (dönüşüm işleci veya oluşturucu) vardır.

- Elipsile temsil edilen argümanlar bulundu.

Derleyici, her bağımsız değişken için bir aday işlevleri kümesi oluşturur. Aday işlevler, bu konumdaki gerçek bağımsız değişkenin biçimsel bağımsız değişken türüne dönüştürülebileceği işlevlerdir.

Her bağımsız değişken için bir "en iyi eşleşen işlevler" kümesi oluşturulur ve seçili işlev tüm kümelerin kesişimidir. Kesişim birden fazla işlev içeriyorsa, aşırı yükleme belirsizdir ve bir hata oluşturur. Sonunda seçilen işlev, her zaman en az bir bağımsız değişken için gruptaki diğer işlevlerden daha iyi bir eşleşmedir. Net bir kazanan yoksa, işlev çağrısı bir hata oluşturur.

Aşağıdaki bildirimleri göz önünde bulundurun `Variant 2`(aşağıdaki tartışmada tanımlama için işlevler , ve `Variant 3`, işaretlenmiştir): `Variant 1`

```cpp
Fraction &Add( Fraction &f, long l );       // Variant 1
Fraction &Add( long l, Fraction &f );       // Variant 2
Fraction &Add( Fraction &f, Fraction &f );  // Variant 3

Fraction F1, F2;
```

Aşağıdaki ifadeyi göz önünde bulundurun:

```cpp
F1 = Add( F2, 23 );
```

Önceki deyim iki küme oluşturur:

|Set 1: Tür Kesirilk Bağımsız Değişkeni Olan Aday İşlevler|Set 2: İkinci Bağımsız Değişkeni **Int** Türüne Dönüştürülebilen Aday İşlevler|
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|Varyant 1|Varyant 1 **(int** standart bir dönüştürme kullanılarak **uzun** dönüştürülebilir)|
|Varyant 3||

Set 2'deki işlevler, gerçek parametre türünden resmi parametre türüne örtülü dönüşümler bulunan işlevlerdir ve bu işlevler arasında gerçek parametre türünü resmi parametre türüne dönüştürmenin "maliyetinin" en küçük olduğu bir işlev vardır.

Bu iki kümenin kesişimi Varyant 1'dir. Belirsiz bir işlev çağrısıörneği:

```cpp
F1 = Add( 3, 6 );
```

Önceki işlev çağrısı aşağıdaki kümeleri oluşturur:

|Set 1: Tür **int** İlk Bağımsız Değişkeni olan aday işlevleri|Set 2: Tip **int'in** İkinci Bağımsız Değişkenine Sahip Aday İşlevler|
|---------------------------------------------------------------------|----------------------------------------------------------------------|
|Varyant 2 **(int** standart bir dönüşüm kullanılarak **uzun** dönüştürülebilir)|Varyant 1 **(int** standart bir dönüştürme kullanılarak **uzun** dönüştürülebilir)|

Bu iki kümenin kesişimi boş olduğundan, derleyici bir hata iletisi oluşturur.

Bağımsız değişken eşleştirmesi için, *n* varsayılan bağımsız değişkenleri olan bir işlev, her biri farklı sayıda bağımsız değişkene sahip *n*+1 ayrı işlevler olarak kabul edilir.

Elipsler (...) joker karakter görevi görür; herhangi bir gerçek argüman eşleşir. Aşırı yüklü işlev kümelerinizi aşırı özenle tasarlamazsanız, birçok belirsiz kümeye yol açabilir.

> [!NOTE]
> Aşırı yüklü işlevlerin belirsizliği, bir işlev çağrısına karşılaşılıncaya kadar belirlenemez. Bu noktada, kümeler işlev çağrısındaki her bağımsız değişken için oluşturulur ve açık bir aşırı yüklemenin var olup olmadığını belirleyebilirsiniz. Bu, belirsizliklerin belirli bir işlev çağrısı tarafından uyarılanıncaya kadar kodunuzda kalabileceğini anlamına gelir.

## <a name="argument-type-differences"></a>Bağımsız Değişken Türü Farkları

Aşırı yüklenmiş işlevler, farklı başlatıcıları olan bağımsız değişken türlerini ayırt eder. Bu nedenle, belirli türden bir bağımsız değişken ve bu türe yapılan bir başvuru, aşırı yükleme amaçları için aynı olarak kabul edilir. Aynı başlatıcıları aldıkları için aynı olarak kabul edilirler. Örneğin `max( double, double )`, `max( double &, double & )` ile aynı olarak kabul edilir. Böyle iki işlevin bildirilmesi bir hataya neden olur.

Aynı nedenle, **const** veya **volatile** tarafından değiştirilen bir türün işlev bağımsız değişkenleri, aşırı yükleme amacıyla temel türden farklı şekilde ele alınmaz.

Ancak, işlev aşırı yükleme mekanizması **const** ve **uçucu** ve temel türüne başvurular tarafından nitelikli başvurular arasında ayırt edebilirsiniz. Aşağıdaki gibi kodları mümkün kılar:

```cpp
// argument_type_differences.cpp
// compile with: /EHsc /W3
// C4521 expected
#include <iostream>

using namespace std;
class Over {
public:
   Over() { cout << "Over default constructor\n"; }
   Over( Over &o ) { cout << "Over&\n"; }
   Over( const Over &co ) { cout << "const Over&\n"; }
   Over( volatile Over &vo ) { cout << "volatile Over&\n"; }
};

int main() {
   Over o1;            // Calls default constructor.
   Over o2( o1 );      // Calls Over( Over& ).
   const Over o3;      // Calls default constructor.
   Over o4( o3 );      // Calls Over( const Over& ).
   volatile Over o5;   // Calls default constructor.
   Over o6( o5 );      // Calls Over( volatile Over& ).
}
```

### <a name="output"></a>Çıktı

```Output
Over default constructor
Over&
Over default constructor
const Over&
Over default constructor
volatile Over&
```

**Const** ve **geçici** nesnelere işaretçiler de aşırı yükleme amacıyla temel türüne işaretçiler farklı olarak kabul edilir.

## <a name="argument-matching-and-conversions"></a>Bağımsız değişken eşleştirme ve dönüşümler

Derleyici işlev bildirimlerinde bağımsız değişkenlere karşı gerçek bağımsız değişkenleri eşleştirmeye çalıştığında, tam eşleşme bulunamazsa doğru türü elde etmek için standart veya kullanıcı tarafından tanımlanan dönüşümler sağlayabilir. Dönüşümlerin uygulanması aşağıdaki kurallara tabidir:

- Birden fazla kullanıcı tanımlı dönüştürme içeren dönüşüm dizileri dikkate alınmaz.

- Ara dönüşümler kaldırılarak kısaltılabilen dönüşüm dizileri dikkate alınmaz.

Varsa, dönüşümlerin ortaya çıkan sırası en iyi eşleşen sıra olarak adlandırılır. Standart dönüşümleri kullanarak **imzasız uzun** yazmaya türü **int** nesnesini dönüştürmenin birkaç yolu vardır [(Standart Dönüşümler'de](../cpp/standard-conversions.md)açıklanmıştır):

- **Int'den** **uzuna** ve daha sonra **uzundan** **imzasız uzuna**dönüştürün.

- **Int'den** **imzasız uzuna**dönüştürün.

İlk sıra, istenilen hedefe ulaşsa da, en iyi eşleşen dizi değildir — daha kısa bir sıra vardır.

Aşağıdaki tablo, hangi dizinin en iyi eşleşme olduğunu belirlemede sınırlı etkiye sahip önemsiz dönüşümler adı verilen bir dönüşüm grubunu gösterir. Önemsiz dönüşümlerin sıra seçimini etkilediği durumlar tabloyu izleyen listede açıklanır.

### <a name="trivial-conversions"></a>Önemsiz Dönüşümler

|Türden Dönüştür|Türe Dönüştür|
|-----------------------|---------------------|
|*tür adı*|*tür adı***&**|
|*tür adı***&**|*tür adı*|
|*tür-isim* **[ ]**|*tür adı*__\*__|
|*tür adı* **(** bağımsız *değişken-listesi* **)**|**(** __\*__ *tür adı* ) **(** bağımsız *değişken listesi* **)**|
|*tür adı*|**const** *tür adı*|
|*tür adı*|**uçucu** *tür adı*|
|*tür adı*__\*__|**const** *tür adı*__\*__|
|*tür adı*__\*__|**uçucu** *tür adı*__\*__|

Dönüşümlerin denenme sırası aşağıdaki gibidir:

1. Tam eşleşme. İşlevin çağrıldığı türler ile işlev prototipinde bildirilen türler arasındaki tam eşleşme her zaman en iyi eşleşmedir. Önemsiz dönüşüm dizileri tam eşleşmeler olarak sınıflandırılır. Ancak, bu dönüşümlerden hiçbirini yapmayan diziler, dönüştüren dizilerden daha iyi kabul edilir:

   - İşaretçiden işaretçiye const 'a`type` <strong>\*</strong> **(const'a).** `type` <strong>\*</strong> **const**

   - İşaretçiden işaretçiye,`type` <strong>\*</strong> **uçucuya** **(uçucuya)** `type` <strong>\*</strong>kadar.

   - Referanstan const'a`type` **&** `type` **&** **(const'a)** gönderme. **const**

   - `type` **&** `type` **&** **Referanstan,** uçucu ya da uçucu ya da **uçucu** ya da

1. Promosyonları kullanarak eşleştirin. Yalnızca integral promosyonlar, **float'tan** **çifte**dönüşümler ve önemsiz dönüşümler içeren tam bir eşleşme olarak sınıflandırılmayan tüm diziler, promosyonlar kullanılarak eşleşin olarak sınıflandırılır. Herhangi bir tam eşleşme kadar iyi bir eşleşme olmasa da, promosyonları kullanan bir eşleşme standart dönüşümleri kullanan bir eşleşmeden daha iyidir.

1. Standart dönüşümleri kullanarak eşleştirin. Yalnızca standart dönüşümler ve önemsiz dönüşümler içeren promosyonlar kullanılarak tam eşleşme veya eşleşme olarak sınıflandırılmayan tüm sıralar, standart dönüşümler kullanılarak eşleme olarak sınıflandırılır. Bu kategoride aşağıdaki kurallar uygulanır:

   - Bir işaretçiden türemiş sınıfa, işaretçinin doğrudan veya dolaylı taban sınıfa dönüştürülmesi `void *` veya `const void *`.

   - Bir işaretçiden türetilmiş sınıfa, bir işaretçinin taban sınıfa dönüştürülmesi, taban sınıfın doğrudan taban sınıfa ne kadar yakın olduğu yla daha iyi eşleşme sağlar. Sınıf hiyerarşisinin aşağıdaki şekilde gösterildiği gibi olduğunu varsayalım.

![Tercih edilen dönüşümlerin grafiği](../cpp/media/vc391t1.gif "Tercih edilen dönüşümlerin grafiği") <br/>
Tercih edilen dönüşümleri gösteren grafik

Türden `D*` türe `C*` dönüştürme, türden `D*` türe `B*`dönüştürmeye tercih edilir. Benzer şekilde, `D*` türden `B*` türe dönüştürme, türden `D*` `A*`türe dönüştürmeye tercih edilir.

Aynı kural başvuru dönüşümleri için de geçerlidir. Türden `D&` türe `C&` dönüştürme, türden `D&` türe `B&`dönüştürmeye ve benzerine tercih edilir.

Aynı kural, üye işaretçisi dönüşümleri için de geçerlidir. Türden `T D::*` türe `T C::*` dönüştürme, türden `T D::*` türe `T B::*`dönüştürmeye ve `T` benzerlerine (üyenin türü nerede) tercih edilir.

Önceki kural yalnızca belirli bir türetme yolu boyunca geçerlidir. Aşağıdaki şekilde gösterilen grafiği göz önünde bulundurun.

![Tercih edilen dönüşümleri gösteren birden çok&#45;kalıtım](../cpp/media/vc391t2.gif "Tercih edilen dönüşümleri gösteren birden çok&#45;kalıtım") <br/>
Tercih edilen dönüşümleri gösteren çoklu devralma grafiği

Türden `C*` türe `B*` dönüştürme, türden `C*` türe `A*`dönüştürmeye tercih edilir. Bunun nedeni, aynı yolda olmaları ve `B*` daha yakın olmalarıdır. Ancak, türden `C*` türe `D*` dönüştürme türüne dönüştürme `A*`tercih edilir; dönüşümler farklı yolları izlediğinden tercih yoktur.

1. Kullanıcı tanımlı dönüşümlerle eşleştirin. Bu sıra tam eşleşme, promosyonları kullanan bir eşleşme veya standart dönüşümleri kullanan bir eşleşme olarak sınıflandırılamaz. Dizi, kullanıcı tanımlı dönüşümlerle eşleşecek şekilde yalnızca kullanıcı tanımlı dönüşümler, standart dönüşümler veya önemsiz dönüşümler içermelidir. Kullanıcı tanımlı dönüşümlerle eşleşen bir eşleşme, elipsli bir eşleşmeden daha iyi olarak kabul edilir, ancak standart dönüşümlerle eşleşen bir eşleşme kadar iyi değildir.

1. Elipsile eşleştir. Bildirimdeki bir elipsle eşleşen herhangi bir dizi, elipsile eşleşen bir dizi olarak sınıflandırılır. En zayıf eşleşme olarak kabul edilir.

Yerleşik promosyon veya dönüşüm yoksa kullanıcı tanımlı dönüşümler uygulanır. Bu dönüşümler, eşleşen bağımsız değişken türüne göre seçilir. Aşağıdaki kodu inceleyin:

```cpp
// argument_matching1.cpp
class UDC
{
public:
   operator int()
   {
      return 0;
   }
   operator long();
};

void Print( int i )
{
};

UDC udc;

int main()
{
   Print( udc );
}
```

Sınıf `UDC` için kullanılabilir kullanıcı tanımlı dönüşümler tür **int** ve type **long'dan**gelir. Bu nedenle, derleyici eşleşen nesnenin türü için dönüşümleri `UDC`dikkate alır: . **Int'e** dönüştürme vardır ve seçilir.

Bağımsız değişkenleri eşleştirme işlemi sırasında, standart dönüşümler hem bağımsız değişkene hem de kullanıcı tarafından tanımlanan dönüştürmenin sonucuna uygulanabilir. Bu nedenle, aşağıdaki kod çalışır:

```cpp
void LogToFile( long l );
...
UDC udc;
LogToFile( udc );
```

Önceki örnekte, kullanıcı tanımlı dönüştürme, **işleç uzun**, `udc` **uzun**yazın dönüştürmek için çağrılır. Uzun türe kullanıcı tanımlı dönüştürme tanımlanmamış **olsaydı,** dönüştürme aşağıdaki gibi `UDC` devam ederdi: Tür, kullanıcı tanımlı dönüştürme kullanılarak **int** türüne dönüştürülürdü. Daha sonra, bildirimdeki bağımsız değişkenle eşleşecek şekilde, tür **int'ten** **uzun** türe standart dönüştürme uygulanmış olur.

Bir bağımsız değişkenle eşleşecek şekilde kullanıcı tarafından tanımlanan dönüşümler gerekiyorsa, en iyi eşleşmeyi değerlendirirken standart dönüşümler kullanılmaz. Birden fazla aday işlev kullanıcı tarafından tanımlanmış bir dönüştürme gerektirse bile, işlevler eşit kabul edilir. Örneğin:

```cpp
// argument_matching2.cpp
// C2668 expected
class UDC1
{
public:
   UDC1( int );  // User-defined conversion from int.
};

class UDC2
{
public:
   UDC2( long ); // User-defined conversion from long.
};

void Func( UDC1 );
void Func( UDC2 );

int main()
{
   Func( 1 );
}
```

Tür `Func` **int** türünü sınıf türü bağımsız değişkenine dönüştürmek için kullanıcı tanımlı bir dönüştürme gerektirir. Olası dönüşümler şunlardır:

- **Tür int** türünden `UDC1` türüne (kullanıcı tanımlı dönüştürme) dönüştürün.

- Yazı **int'ten** **uzun**yazıya dönüştürme ; sonra türe `UDC2` dönüştürün (iki adımlı dönüştürme).

İkincisi hem standart bir dönüştürme hem de kullanıcı tarafından tanımlanan dönüştürme gerektirmese de, iki dönüşüm yine de eşit kabul edilir.

> [!NOTE]
> Kullanıcı tanımlı dönüşümler, başlangıç (dönüşüm işlevi) tarafından inşaat veya dönüşüm tarafından dönüşüm olarak kabul edilir. En iyi eşleşme düşünüldüğünde her iki yöntem de eşit olarak kabul edilir.

## <a name="argument-matching-and-the-this-pointer"></a>Bağımsız değişken eşleştirme ve bu işaretçi

Sınıf üye işlevleri **statik**olarak bildirilip belirtilmesine bağlı olarak farklı şekilde ele alınır. Statik olmayan işlevler **bu** işaretçiyi sağlayan örtük bir bağımsız değişkene sahip olduğundan, statik olmayan işlevler statik işlevlerden bir bağımsız değişkene sahip olarak kabul edilir; aksi takdirde, aynı şekilde beyan edilir.

Bu statik olmayan üye işlevler, zımni **bu** işaretçinin işlevin çağrıldığı nesne türüyle eşleşmesini veya aşırı yüklenen işleçler için ilk bağımsız değişkenin işlecinin uygulandığı nesneyle eşleşmesini gerektirir. (Aşırı yüklü operatörler hakkında daha fazla bilgi için [bkz.](../cpp/operator-overloading.md)

Aşırı yüklenilen işlevlerde diğer bağımsız değişkenlerin aksine, geçici nesneler tanıtılır ve **bu** işaretçi bağımsız değişkenini eşleştirmeye çalışırken dönüştürme girişiminde bulunulmamada.

`->` Üye seçim işleci sınıfın `class_name`bir üye işlevine erişmek için kullanıldığında, **bu** işaretçi bağımsız değişkeninin `class_name * const`bir türü vardır. Üyeler **const** veya **uçucu**olarak bildirilirse, `volatile class_name * const`türleri ve , sırasıyla. `const class_name * const`

`.` üye seçme işleci, örtük `&` (adres) işlecinin nesne adının önüne eklenmesi dışında tamamen aynı şekilde çalışır. Aşağıdaki örnekte, bunun nasıl çalıştığı gösterilmektedir:

```cpp
// Expression encountered in code
obj.name

// How the compiler treats it
(&obj)->name
```

`->*` Ve `.*` (üye işaretçi) işleçlerinin sol operand bağımsız `.` değişken `->` eşleştirme ile ilgili olarak ve (üye seçimi) operatörleri ile aynı şekilde tedavi edilir.

## <a name="ref-qualifiers-on-member-functions"></a><a name="ref-qualifiers"></a>Üye işlevlerde ref elemeleri

Ref niteleyicileri, bir üye işlevin, **işaret** ettiği nesnenin bir rvalue veya lvalue olup olmadığına göre aşırı yüklenmesini mümkün kılar.  Bu özellik, veri işaretçisi erişimi sağlamamayı seçtiğiniz senaryolarda gereksiz kopyalama işlemlerini önlemek için kullanılabilir. Örneğin, sınıfın `C` oluşturucudaki bazı verileri başlatılmasını varsayalım ve bu verilerin `get_data()`bir kopyasını üye işlevde döndürür. Türdeki `C` bir nesne yok olmak üzere olan bir rvalue ise, `get_data() &&` derleyici verileri kopyalamak yerine hareket ettiren aşırı yüklemeyi seçer.

```cpp
#include <iostream>
#include <vector>

using namespace std;

class C
{

public:
    C() {/*expensive initialization*/}
    vector<unsigned> get_data() &
    {
        cout << "lvalue\n";
        return _data;
    }
    vector<unsigned> get_data() &&
    {
        cout << "rvalue\n";
        return std::move(_data);
    }

private:
    vector<unsigned> _data;
};

int main()
{
    C c;
    auto v = c.get_data(); // get a copy. prints "lvalue".
    auto v2 = C().get_data(); // get the original. prints "rvalue"
    return 0;
}
```

## <a name="restrictions-on-overloading"></a>Aşırı yüklemeyle ilgili kısıtlamalar

Çeşitli kısıtlamalar, kabul edilebilir bir aşırı yüklü işlevler kümesini yönetir:

- Aşırı yüklenen işlevler kümesindeki herhangi iki işlevin farklı bağımsız değişken listeleri olmalıdır.

- Yalnızca iade türüne dayalı olarak aynı türde bağımsız değişken listeleri içeren işlevleri aşırı yükleme bir hatadır.

     **Microsoft'a Özgü**

**İşleç yeniyi** yalnızca iade türüne göre aşırı yükleyebilirsiniz – özellikle, belirtilen bellek modeli değiştirici temelinde.

**END Microsoft Özel**

- Üye işlevler yalnızca biri statik, diğeri statik olmayan temel alınarak aşırı yüklenmez.

- **typedef** bildirimleri yeni türleri tanımlamaz; varolan türler için eşanlamlılar sunarlar. Aşırı yükleme mekanizmasını etkilemezler. Aşağıdaki kodu inceleyin:

    ```cpp
    typedef char * PSTR;

    void Print( char *szToPrint );
    void Print( PSTR szToPrint );
    ```

   Önceki iki işlevin aynı bağımsız değişken listeleri vardır. `PSTR`türü `char *`için eşanlamlıdır. Üye kapsamında, bu kod bir hata oluşturur.

- Numaralandırılmış türleri farklı türleri dir ve aşırı yüklü işlevleri ayırt etmek için kullanılabilir.

- "Dizi" ve "işaretçi" türleri, aşırı yüklenen işlevler arasında ayrım yapmak amacıyla, ancak yalnızca tek boyutlu diziler için aynı kabul edilir. Bu nedenle bu aşırı yüklü işlevler çakışıyor ve bir hata iletisi oluşturuyor:

    ```cpp
    void Print( char *szToPrint );
    void Print( char szToPrint[] );
    ```

   Çarpma boyutlanmış diziler için, ikinci ve tüm başarılı boyutlar türün bir parçası olarak kabul edilir. Bu nedenle, aşırı yüklü işlevleri ayırt etmek için kullanılır:

    ```cpp
    void Print( char szToPrint[] );
    void Print( char szToPrint[][7] );
    void Print( char szToPrint[][9][42] );
    ```

## <a name="overloading-overriding-and-hiding"></a>Aşırı yükleme, geçersiz kılma ve gizleme

Aynı kapsamda aynı ada ait iki işlev bildirimi, aynı işleve veya aşırı yüklenen iki ayrı işleve başvurabilir. Bildirimlerin bağımsız değişken listeleri eşdeğer türlerin bağımsız değişkenlerini içeriyorsa (önceki bölümde açıklandığı gibi), işlev bildirimleri aynı işleve başvurur. Aksi takdirde, aşırı yükleme kullanılarak seçilen iki farklı işlevi ifade ederler.

Sınıf kapsamı kesinlikle gözlenir; bu nedenle, taban sınıfta bildirilen bir işlev, türemiş bir sınıfta bildirilen bir işlevle aynı kapsamda değildir. Türemiş bir sınıftaki bir işlev taban sınıfta sanal bir işlevle aynı ada sahip olarak bildirilirse, türemiş sınıf işlevi taban sınıf işlevini *geçersiz kılar.* Daha fazla bilgi için [Sanal İşlevler'e](../cpp/virtual-functions.md)bakın.

Taban sınıf işlevi 'sanal' olarak bildirilmemişse, türetilmiş sınıf *işlevinin gizlediği* söylenir. Hem geçersiz kılma hem de gizleme aşırı yüklemeden farklıdır.

Blok kapsamı kesinlikle gözlenir; bu nedenle, dosya kapsamında bildirilen bir işlev yerel olarak bildirilen bir işlevle aynı kapsamda değildir. Yerel olarak bildirilen bir işlev, dosya kapsamında bildirilen işlevle aynı ada sahipse, yerel olarak bildirilen işlev aşırı yüklemeye neden olmak yerine dosya kapsamı işlevini gizler. Örneğin:

```cpp
// declaration_matching1.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
void func( int i )
{
    cout << "Called file-scoped func : " << i << endl;
}

void func( char *sz )
{
   cout << "Called locally declared func : " << sz << endl;
}

int main()
{
   // Declare func local to main.
   extern void func( char *sz );

   func( 3 );   // C2664 Error. func( int ) is hidden.
   func( "s" );
}
```

Önceki kod işlevden `func`iki tanım gösterir. Tür `char *` bir argüman alır tanımı `main` **extern** deyimi nedeniyle yereldir. Bu nedenle, tür **int** bir argüman alır tanımı gizlidir `func` ve ilk çağrı hata.

Aşırı yüklenen üye işlevler için, işlevin farklı sürümlerine farklı erişim ayrıcalıkları verilebilir. Bunlar hala çevreleyen sınıfın kapsamında olarak kabul edilir ve bu nedenle aşırı işlevler vardır. Üye işlevin `Deposit` aşırı yüklendiği aşağıdaki kodu göz önünde bulundurun; bir sürümü genel, diğer, özel.

Bu örneğin amacı, para `Account` yatırma gerçekleştirmek için doğru bir parolanın gerekli olduğu bir sınıf sağlamaktır. Aşırı yükleme kullanılarak yapılır.

Çağrı, `Deposit` özel `Account::Deposit` üye işlevini çağırır. Bu çağrı, `Account::Deposit` bir üye işlev olduğundan ve sınıfın özel üyelerine erişimi olduğundan doğrudur.

```cpp
// declaration_matching2.cpp
class Account
{
public:
   Account()
   {
   }
   double Deposit( double dAmount, char *szPassword );

private:
   double Deposit( double dAmount )
   {
      return 0.0;
   }
   int Validate( char *szPassword )
   {
      return 0;
   }

};

int main()
{
    // Allocate a new object of type Account.
    Account *pAcct = new Account;

    // Deposit $57.22. Error: calls a private function.
    // pAcct->Deposit( 57.22 );

    // Deposit $57.22 and supply a password. OK: calls a
    //  public function.
    pAcct->Deposit( 52.77, "pswd" );
}

double Account::Deposit( double dAmount, char *szPassword )
{
   if ( Validate( szPassword ) )
      return Deposit( dAmount );
   else
      return 0.0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Fonksiyonlar (C++)](../cpp/functions-cpp.md)
