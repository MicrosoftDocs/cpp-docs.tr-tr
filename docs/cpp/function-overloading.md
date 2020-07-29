---
title: İşlev Aşırı Yüklemesi
ms.date: 03/27/2019
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
ms.openlocfilehash: 0eaaf5c8fd18d4d00652107a5a2071b2f5774d7c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232319"
---
# <a name="function-overloading"></a>İşlev Aşırı Yüklemesi

C++, aynı kapsamda aynı ada sahip birden fazla işlevin belirtilmesini sağlar. Bu işlevlere *aşırı yüklenmiş* işlevler denir. Aşırı yüklenmiş işlevler, bağımsız değişkenlerin türlerine ve sayısına bağlı olarak bir işlev için farklı semantikler vermenizi sağlar.

Örneğin, `print` bir bağımsız değişken alan bir işlev, `std::string` türünde bir bağımsız değişken alan bir çok farklı görevi gerçekleştirebilir **`double`** . Aşırı yükleme, veya gibi adları kullanmak zorunda kalmanızı `print_string` sağlar `print_double` . Derleme zamanında derleyici, çağıran tarafından geçirilen bağımsız değişkenlerin türüne göre hangi aşırı yüklemeyi kullanacağınızı seçer.  `print(42.0)`Öğesini çağırırsanız, `void print(double d)` işlev çağrılır. `print("hello world")`Öğesini çağırdığınızda `void print(std::string)` aşırı yükleme çağrılacaktır.

Hem üye işlevlerini hem de üye olmayan işlevleri aşırı yükleyebilirsiniz. Aşağıdaki tabloda, C++'nın aynı kapsamda aynı ana sahip işlev gruplarını birbirinden ayırmak için işlev bildiriminin hangi bölümlerini kullandığını gösterir.

### <a name="overloading-considerations"></a>Aşırı Yükleme Hakkında Önemli Noktalar

|İşlev Bildirimi Öğesi|Aşırı yükleme için kullanılır mı?|
|----------------------------------|---------------------------|
|İşlevin dönüş türü|Hayır|
|Bağımsız değişkenlerin sayısı|Yes|
|Bağımsız değişkenlerin türü|Yes|
|Üç nokta için varlık veya yokluğu|Yes|
|Adların kullanımı **`typedef`**|Hayır|
|Belirtilmemiş dizi sınırları|Hayır|
|**`const`** veya**`volatile`**|Evet, tüm işleve uygulandığında|
|[Ref niteleyicileri](#ref-qualifiers)|Yes|

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

Varsayılan bağımsız değişken, işlev türünün bir parçası olarak kabul edilmez. Bu nedenle, aşırı yüklenmiş işlevler seçilmede kullanılmaz. Yalnızca kendi varsayılan bağımsız değişkenlerinde farklı olan iki işlevde, aşırı yüklenmiş işlevler yerine birden çok tanım dikkate alınır.

Varsayılan bağımsız değişkenler, aşırı yüklenmiş işleçler için sağlanamaz.

## <a name="argument-matching"></a>Bağımsız Değişken Eşleştirme

Geçerli kapsamdaki işlev bildirimlerinin en iyi eşleşmesi için, işlev çağrısında sağlanan bağımsız değişkenlerle, aşırı yüklenmiş işlevler seçilir. Uygun bir işlev bulunursa, bu işlev çağrılır. Bu bağlamda "uygun", aşağıdakilerden biri olabilir:

- Tam eşleşme bulundu.

- Önemsiz bir dönüştürme gerçekleştirildi.

- İntegral yükseltme gerçekleştirildi.

- İstenen bağımsız değişken türüne standart bir dönüştürme var.

- İstenen bağımsız değişken türüne Kullanıcı tanımlı bir dönüştürme (dönüştürme işleci veya Oluşturucu) var.

- Üç nokta ile temsil edilen bağımsız değişkenler bulundu.

Derleyici, her bağımsız değişken için bir aday işlevleri kümesi oluşturur. Aday işlevleri, o konumdaki gerçek bağımsız değişkenin biçimsel bağımsız değişken türüne dönüştürülebileceği işlevlerdir.

Her bağımsız değişken için bir "en iyi eşleştirme işlevleri" kümesi oluşturulur ve seçilen işlev tüm kümelerdeki kesişimden oluşur. Kesişmeyle birden fazla işlev varsa, aşırı yükleme belirsizdir ve bir hata oluşturur. Son olarak seçilen işlev, en az bir bağımsız değişken için her zaman gruptaki diğer her işlevle daha iyi bir eşleşmedir. Açık bir yarışmak yoksa, işlev çağrısı bir hata oluşturur.

Aşağıdaki bildirimleri göz önünde bulundurun (işlevler, `Variant 1` ve, `Variant 2` `Variant 3` aşağıdaki tartışmadaki tanımlama için):

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

Yukarıdaki ifade iki küme oluşturur:

|1: kesir türünde Ilk bağımsız değişkene sahip aday Işlevleri|2. ayarla: Ikinci bağımsız değişkeni türüne dönüştürülebileceği aday Işlevleri**`int`**|
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|Varyant 1|Varyant 1 ( **`int`** **`long`** Standart dönüştürme kullanılarak dönüştürülebilir)|
|Varyant 3||

Set 2 ' deki işlevler, gerçek parametre türünden biçimsel parametre türüne örtük dönüştürmeler olan işlevlerdir ve bu tür işlevlerde gerçek parametre türünü resmi parametre türüne dönüştürmenin "maliyeti" değeri en küçüğü olur.

Bu iki kümenin kesişimi varyant 1 ' dir. Belirsiz bir işlev çağrısına bir örnek:

```cpp
F1 = Add( 3, 6 );
```

Önceki işlev çağrısı aşağıdaki kümeleri oluşturur:

|Set 1: Ilk bağımsız değişken türünde olan aday Işlevleri**`int`**|2: tür Ikinci bağımsız değişkenine sahip aday Işlevleri ayarla**`int`**|
|---------------------------------------------------------------------|----------------------------------------------------------------------|
|Varyant 2 ( **`int`** **`long`** Standart dönüştürme kullanılarak dönüştürülebilir)|Varyant 1 ( **`int`** **`long`** Standart dönüştürme kullanılarak dönüştürülebilir)|

Bu iki kümenin kesişimi boş olduğundan, derleyici bir hata iletisi oluşturur.

Bağımsız değişken eşleştirme için, *n* varsayılan bağımsız değişkenlere sahip bir işlev, her biri farklı sayıda bağımsız değişkene sahip *n*+ 1 ayrı işlev olarak değerlendirilir.

Üç nokta (...) bir joker karakter olarak davranır; herhangi bir gerçek bağımsız değişkenle eşleşir. Aşırı yüklenmiş işlev kümelerinizi çok dikkatli bir şekilde tasarlamazsanız, bu birçok belirsiz kümesine yol açabilir.

> [!NOTE]
> Aşırı yüklenmiş işlevlerin belirsizlik, bir işlev çağrısıyla karşılaşana kadar belirlenemez. Bu noktada, kümeler işlev çağrısındaki her bağımsız değişken için oluşturulur ve belirsiz bir aşırı yükleme olup olmadığını belirleyebilirsiniz. Bu, belirsizlikleri belirli bir işlev çağrısıyla alınana kadar kodunuzda kalabileceği anlamına gelir.

## <a name="argument-type-differences"></a>Bağımsız Değişken Türü Farkları

Aşırı yüklenmiş işlevler, farklı başlatıcıları olan bağımsız değişken türlerini ayırt eder. Bu nedenle, belirli türden bir bağımsız değişken ve bu türe yapılan bir başvuru, aşırı yükleme amaçları için aynı olarak kabul edilir. Aynı başlatıcıları aldıkları için aynı olarak kabul edilirler. Örneğin `max( double, double )`, `max( double &, double & )` ile aynı olarak kabul edilir. Böyle iki işlevin bildirilmesi bir hataya neden olur.

Aynı nedenden dolayı, veya tarafından değiştirilen bir türün işlev bağımsız değişkenleri **`const`** , **`volatile`** aşırı yükleme amaçları için temel türden farklı olarak değerlendirilmez.

Ancak, işlev aşırı yükleme mekanizması, ve tarafından nitelenen başvuruları **`const`** **`volatile`** ve temel türe başvuruları birbirinden ayırt edebilir. Aşağıdaki gibi bir kod getirir:

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

**`const`** Ve nesnelerinin işaretçileri, **`volatile`** aşırı yükleme amaçları için temel türe işaretçilerden farklı olarak değerlendirilir.

## <a name="argument-matching-and-conversions"></a>Bağımsız değişken eşleştirme ve dönüştürmeleri

Derleyici gerçek bağımsız değişkenleri işlev bildirimlerinde bağımsız değişkenlerle eşleştirmeye çalıştığında, tam eşleşme bulunamazsa doğru türü elde etmek için standart veya Kullanıcı tanımlı dönüştürmeler sağlayabilir. Dönüştürmelerin uygulaması bu kurallara tabidir:

- Birden fazla Kullanıcı tanımlı dönüştürme içeren dönüştürmelerin dizileri dikkate alınmıyor.

- Ara dönüştürmeleri kaldırarak kısaltılması gereken dönüştürme dizileri göz önünde bulundurulmaz.

Varsa, dönüştürme sırası en iyi eşleşen sıra olarak adlandırılır. **`int`** **`unsigned long`** Standart dönüşümler ( [Standart dönüşümlerde](../cpp/standard-conversions.md)açıklanmıştır) kullanarak türü bir nesneyi türüne dönüştürmenin birkaç yolu vardır:

- Değerinden öğesine **`int`** **`long`** ve öğesinden öğesine dönüştürün **`long`** **`unsigned long`** .

- ' Dan ' a Dönüştür **`int`** **`unsigned long`** .

İlk sıra, istenen hedefe ulaşır, ancak en iyi eşleşen sıra, daha kısa bir sıra vardır.

Aşağıdaki tabloda, en iyi eşleşen sırayı belirlemek için sınırlı bir etkiye sahip olan önemsiz dönüştürmeler adlı bir dönüştürme grubu gösterilmektedir. Önemsiz dönüştürmelerin dizi seçimini etkilediği örnekler, tablonun takip ettiği listede ele alınmıştır.

### <a name="trivial-conversions"></a>Önemsiz dönüşümler

|Türden Dönüştür|Türe Dönüştür|
|-----------------------|---------------------|
|*tür adı*|*tür adı***&**|
|*tür adı***&**|*tür adı*|
|*tür adı* **[]**|*tür adı*__\*__|
|*tür adı* **(** *bağımsız değişken listesi* **)**|**(** __\*__ *tür-adı* **) (** *bağımsız değişken listesi* **)**|
|*tür adı*|**`const`***tür adı*|
|*tür adı*|**`volatile`***tür adı*|
|*tür adı*__\*__|**`const`***tür adı*__\*__|
|*tür adı*__\*__|**`volatile`***tür adı*__\*__|

Dönüştürmelerin denenme sırası aşağıdaki gibidir:

1. Tam eşleşme. İşlevin çağrıldığı türler arasında tam eşleşme ve işlev prototipte belirtilen türler her zaman en iyi eşleşmedir. Önemsiz dönüştürmelerin dizileri tam eşleşmeler olarak sınıflandırılır. Ancak, bu Dönüştürmelere sahip olmayan sıralar, dönüştürülecek dizilerden daha iyi kabul edilir:

   - İşaretçiden **`const`** ( `type` <strong>\*</strong> to **`const`** `type` <strong>\*</strong> ) işaretçisine.

   - İşaretçiden **`volatile`** ( `type` <strong>\*</strong> to **`volatile`** `type` <strong>\*</strong> ) işaretçisine.

   - Başvuruya, başvuruya **`const`** ( `type` **&** için **`const`** `type` **&** ).

   - Başvuruya, başvuruya **`volatile`** ( `type` **&** için **`volatile`** `type` **&** ).

1. Yükseltmeleri kullanarak eşleştirin. Yalnızca integral yükseltmeleri içeren tam eşleşme olarak sınıflandırılmayan herhangi bir sıra, ' den **`float`** **`double`** ve önemsiz dönüştürmelerde, promosyonlar kullanılarak eşleşme olarak sınıflandırılır. Tam eşleşme kadar iyi bir eşleşme olmasa da, promosyonları kullanan bir eşleşme standart dönüştürmeleri kullanarak bir eşleşenden daha iyidir.

1. Standart dönüştürmeleri kullanarak eşleştirin. Tam eşleşme olarak sınıflandırılmayan herhangi bir sıra, yalnızca standart dönüştürmeleri ve önemsiz dönüştürmeleri içeren yükseltmeleri kullanarak eşleşme, standart dönüştürmeleri kullanarak bir eşleşme olarak sınıflandırılmaktadır. Bu kategori içinde, aşağıdaki kurallar uygulanır:

   - Bir işaretçiden türetilmiş bir sınıfa, doğrudan veya dolaylı temel sınıfa olan işaretçiye dönüştürme, veya ' a dönüştürmeye tercih edilir `void *` `const void *` .

   - Bir işaretçiden türetilmiş bir sınıfa, taban sınıfına olan işaretçiye dönüştürme, temel sınıfın bir doğrudan taban sınıfına yaklaşmasından daha iyi bir eşleşme üretir. Sınıf hiyerarşisinin aşağıdaki şekilde gösterildiği gibi olduğunu varsayalım.

![Tercih edilen dönüşümler grafiği](../cpp/media/vc391t1.gif "Tercih edilen dönüşümler grafiği") <br/>
Tercih edilen dönüştürmeleri gösteren grafik

Türünden türüne dönüştürme `D*` `C*` , türünden türüne dönüştürme işlemi tercih edilir `D*` `B*` . Benzer şekilde, türünden `D*` türüne dönüştürme, `B*` türünden türüne dönüştürme işlemi tercih edilir `D*` `A*` .

Bu kural, başvuru dönüştürmeleri için geçerlidir. Türünden türüne dönüştürme `D&` `C&` , türünden türüne dönüştürme işlemi tercih edilir `D&` `B&` .

Bu kural, üye işaretçisi dönüştürmeleri için geçerlidir. Türünden türüne dönüştürme `T D::*` `T C::*` , türünden türüne dönüştürme işlemi tercih edilir `T D::*` ve bu `T B::*` nedenle ( `T` üyenin türüdür).

Yukarıdaki kural yalnızca belirli bir türetme yolu üzerinde geçerlidir. Aşağıdaki şekilde gösterilen grafiği göz önünde bulundurun.

![Tercih edilen dönüştürmeleri gösteren birden çok&#45;devralma](../cpp/media/vc391t2.gif "Tercih edilen dönüştürmeleri gösteren birden çok&#45;devralma") <br/>
Tercih edilen dönüştürmeleri gösteren birden çok devralma grafiği

Türünden türüne dönüştürme `C*` `B*` , türünden türüne dönüştürme işlemi tercih edilir `C*` `A*` . Bunun nedeni, aynı yolda olduklarından ve `B*` daha yakından olur. Ancak, tür türünden `C*` türüne dönüştürme, `D*` türe dönüştürmeye tercih değildir `A*` ; dönüşümler farklı yollar izlediğinden hiçbir tercih yoktur.

1. Kullanıcı tanımlı dönüşümlerle Eşleştir. Bu sıra tam eşleşme olarak sınıflandırılmayabilir, promosyonları kullanarak bir eşleşme veya standart dönüştürmeleri kullanarak bir eşleşme olamaz. Sıra, Kullanıcı tanımlı dönüşümlerle eşleşme olarak sınıflandırılacak yalnızca Kullanıcı tanımlı dönüştürmeleri, standart dönüştürmeleri veya önemsiz dönüştürmeleri içermelidir. Kullanıcı tanımlı dönüştürmelerde eşleşme, üç nokta ile eşleşenden daha iyi bir eşleşme olarak değerlendirilir, ancak standart dönüşümlerle eşleşme olarak eşleşme iyi değildir.

1. Üç nokta ile eşleştirin. Bildirimde bir üç nokta ile eşleşen herhangi bir sıra, üç nokta ile eşleşme olarak sınıflandırılır. En zayıf eşleşme olarak kabul edilir.

Yerleşik yükseltme veya dönüştürme yoksa, Kullanıcı tanımlı dönüştürmeler uygulanır. Bu dönüşümler eşleştirmekte olan bağımsız değişkenin türü temelinde seçilir. Aşağıdaki kodu inceleyin:

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

Sınıf için kullanılabilir Kullanıcı tanımlı dönüştürmeler `UDC` tür **`int`** ve türden **`long`** . Bu nedenle, derleyici eşleştirmekte olan nesnenin türü için dönüşümleri kabul eder: `UDC` . **`int`** Var olan bir dönüştürme ve seçilir.

Eşleşen bağımsız değişkenlerin işlenmesi sırasında, standart dönüştürmeler hem bağımsız değişkenine hem de Kullanıcı tanımlı dönüştürmenin sonucuna uygulanabilir. Bu nedenle, aşağıdaki kod işe yarar:

```cpp
void LogToFile( long l );
...
UDC udc;
LogToFile( udc );
```

Yukarıdaki örnekte Kullanıcı tanımlı dönüştürme, **Long işleci**türüne dönüştürülecek şekilde çağrılır `udc` **`long`** . Türe Kullanıcı tanımlı dönüştürme **`long`** tanımlanmazsa, dönüştürmenin şu şekilde devam etmiş olması gerekir: tür, `UDC` **`int`** Kullanıcı tanımlı dönüştürme kullanılarak türe dönüştürüldü. Sonra tür türüne Standart dönüştürme, **`int`** **`long`** bildirimdeki bağımsız değişkenle eşleşecek şekilde uygulandı.

Bir bağımsız değişkenle eşleşmesi gereken kullanıcı tanımlı dönüştürmeler gerekliyse, en iyi eşleşme değerlendirilirken standart dönüşümler kullanılmaz. Birden fazla aday işlevi Kullanıcı tanımlı dönüştürme gerektirse de işlevler eşit kabul edilir. Örnek:

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

Her iki sürümü de `Func` türü **`int`** sınıf türü bağımsız değişkenine dönüştürmek için Kullanıcı tanımlı bir dönüştürme gerektirir. Olası dönüşümler şunlardır:

- Türden türüne Dönüştür **`int`** `UDC1` (Kullanıcı tanımlı dönüştürme).

- Türden türüne Dönüştür, **`int`** **`long`** sonra türe Dönüştür `UDC2` (iki adımlı dönüştürme).

İkincisi bir standart dönüştürme ve Kullanıcı tanımlı dönüştürme gerektirse de, iki dönüştürme hala eşit kabul edilir.

> [!NOTE]
> Kullanıcı tanımlı dönüştürmeler, oluşturma veya başlatma (dönüştürme işlevi) tarafından dönüştürme olarak değerlendirilir. Her iki yöntem de en iyi eşleşme düşünüldüğünde eşit kabul edilir.

## <a name="argument-matching-and-the-this-pointer"></a>Bu işaretçiyle eşleşen bağımsız değişken

Sınıf üyesi işlevleri, olarak bildirilip tanımlanmayacağı gibi farklı şekilde değerlendirilir **`static`** . Statik olmayan işlevlerde işaretçiyi sağlayan örtük bir bağımsız değişken bulunduğundan **`this`** , statik olmayan işlevler statik işlevlerden daha fazla bağımsız değişkene sahip kabul edilir; Aksi takdirde, aynı şekilde bildirilmiştir.

Bu statik olmayan üye işlevleri, örtük **`this`** işaretçinin işlevin çağrıldığı nesne türüyle eşleşmesini gerektirir veya aşırı yüklenmiş işleçler için, ilk bağımsız değişkenin işlecin uygulandığı nesneyle eşleşmesini gerektirir. (Aşırı yüklenmiş işleçler hakkında daha fazla bilgi için bkz. [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md).)

Aşırı yüklenmiş işlevlerde diğer bağımsız değişkenlerden farklı olarak, hiçbir geçici nesne tanıtılmadı ve işaretçi bağımsız değişkeniyle eşleştirmeye çalışırken hiçbir dönüştürme denenmez **`this`** .

`->`Üye seçim işleci, sınıfının bir üye işlevine erişmek için kullanıldığında `class_name` , **`this`** işaretçi bağımsız değişkeni bir türü olur `class_name * const` . Üyeler veya olarak bildirilirse **`const`** **`volatile`** , `const class_name * const` sırasıyla türler ve `volatile class_name * const` ' dir.

`.` üye seçme işleci, örtük `&` (adres) işlecinin nesne adının önüne eklenmesi dışında tamamen aynı şekilde çalışır. Aşağıdaki örnekte, bunun nasıl çalıştığı gösterilmektedir:

```cpp
// Expression encountered in code
obj.name

// How the compiler treats it
(&obj)->name
```

`->*`Ve `.*` (üye işaretçisi) işleçlerinin sol işleneni, `.` ve `->` (üye seçim) işleçleriyle bağımsız değişken eşleştirmesine göre aynı şekilde değerlendirilir.

## <a name="ref-qualifiers-on-member-functions"></a><a name="ref-qualifiers"></a>Üye işlevlerde ref niteleyicileri

Başvuru niteleyicileri, nesnesine göre işaret edilen nesnenin **`this`** bir rvalue veya lvalue olmasına göre bir üye işlevinin aşırı yüklenmesine olanak sağlar.  Bu özellik, verilere işaretçi erişimi sağlamamasını seçtiğiniz senaryolarda gereksiz kopyalama işlemlerini önlemek için kullanılabilir. Örneğin, sınıfın `C` oluşturucusunda bazı verileri Başlatan olduğunu varsayın ve bu verilerin bir kopyasını üye işlevinde döndürür `get_data()` . Türünde bir nesne `C` yok edilmek üzere olan bir rvalue ise, derleyici, `get_data() &&` verileri kopyalamak yerine taşınan aşırı yüklemeyi seçer.

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

## <a name="restrictions-on-overloading"></a>Aşırı yükleme kısıtlamaları

Çeşitli kısıtlamalar, kabul edilebilir bir dizi aşırı yüklenmiş işlevi yönetir:

- Aşırı yüklenmiş işlevlerin bir kümesindeki tüm iki işlev farklı bağımsız değişken listelerine sahip olmalıdır.

- Yalnızca dönüş türüne göre aynı türlerin bağımsız değişken listeleriyle işlevleri aşırı yükleme, bir hatadır.

     **Microsoft'a Özgü**

Yalnızca, belirtilen bellek modeli değiştiricisinin temelinde, yalnızca dönüş türü temelinde **Yeni işleç** aşırı yükleyebilirsiniz.

**SON Microsoft 'a özgü**

- Üye işlevleri, yalnızca bir statik olan ve diğeri statik olmayan bir temel alınarak aşırı yüklenemez.

- **`typedef`** Bildirimler yeni türler tanımlamaz; Bunlar var olan türler için eş anlamlı sözcükler sunar. Aşırı yükleme mekanizmasını etkilemez. Aşağıdaki kodu inceleyin:

    ```cpp
    typedef char * PSTR;

    void Print( char *szToPrint );
    void Print( PSTR szToPrint );
    ```

   Önceki iki işlevin aynı bağımsız değişken listeleri vardır. `PSTR`, türü için bir eş anlamlı `char *` . Üye kapsamında, bu kod bir hata oluşturur.

- Numaralandırılmış türler farklı türlerdir ve aşırı yüklenmiş işlevleri ayırt etmek için kullanılabilir.

- "Array of" ve "Pointer" türleri, aşırı yüklenmiş işlevler arasındaki ayrım amaçları için aynı kabul edilir, ancak yalnızca listedir boyutlaştırılmış diziler için geçerlidir. Bu nedenle, bu aşırı yüklenmiş işlevlerin çakışmasıyla ilgili bir hata iletisi oluşturur:

    ```cpp
    void Print( char *szToPrint );
    void Print( char szToPrint[] );
    ```

   Boyutlandırılmış dizileri çarpmak için ikinci ve tüm izleyen boyutlar türün bir parçası olarak kabul edilir. Bu nedenle, aşırı yüklenmiş işlevler arasında ayrım yapmak için kullanılır:

    ```cpp
    void Print( char szToPrint[] );
    void Print( char szToPrint[][7] );
    void Print( char szToPrint[][9][42] );
    ```

## <a name="overloading-overriding-and-hiding"></a>Aşırı yükleme, geçersiz kılma ve gizleme

Aynı kapsamda aynı ada sahip tüm iki işlev bildirimi aynı işleve veya aşırı yüklenmiş iki ayrı işleve başvurabilir. Bildirimlerin bağımsız değişken listeleri eşdeğer türlerde bağımsız değişkenler içeriyorsa (önceki bölümde açıklandığı gibi), işlev bildirimleri aynı işleve başvurur. Aksi takdirde, aşırı yükleme kullanılarak seçilen iki farklı işleve başvurur.

Sınıf kapsamı kesinlikle gözlemlenmiştir; Bu nedenle, bir temel sınıfta belirtilen bir işlev, türetilmiş bir sınıfta belirtilen bir işlevle aynı kapsamda değildir. Türetilmiş bir sınıftaki bir işlev, temel sınıftaki bir sanal işlevle aynı adla bildirilirse, türetilen sınıf işlevi temel sınıf işlevini *geçersiz kılar* . Daha fazla bilgi için bkz. [sanal işlevler](../cpp/virtual-functions.md).

Temel sınıf işlevi ' Virtual ' olarak bildirilirse, türetilmiş sınıf işlevi onu *gizleyecek* şekilde ifade edilir. Hem geçersiz kılma hem de gizleme aşırı yükleme dışında farklıdır.

Blok kapsamı kesinlikle gözlemlenmiştir; Bu nedenle, dosya kapsamında belirtilen bir işlev yerel olarak tanımlanan bir işlevle aynı kapsamda değildir. Yerel olarak tanımlanan bir işlev, dosya kapsamında belirtilen bir işlevle aynı ada sahipse, yerel olarak belirtilen işlev aşırı yüklemeye neden olmak yerine dosya kapsamlı işlevi gizler. Örnek:

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

Yukarıdaki kod, işlevden iki tanım gösterir `func` . Türünde bir bağımsız değişken alan tanım, `char *` ifadesinin nedeniyle yereldir `main` **`extern`** . Bu nedenle, türünde bir bağımsız değişken alan tanım **`int`** gizlidir ve ilk çağrısı `func` hatalı olur.

Aşırı yüklenmiş üye işlevleri için, işlevin farklı sürümlerine farklı erişim ayrıcalıkları verilebilir. Bunlar, kapsayan sınıfın kapsamında oldukları kabul edilir ve bu nedenle aşırı yüklenmiş işlevlerdir. Üye işlevin aşırı yüklendiği aşağıdaki kodu düşünün `Deposit` ; bir sürüm ortak, diğeri, özel.

Bu örneğin amacı, `Account` mevduat yapmak için doğru parolanın gerekli olduğu bir sınıf sağlamaktır. Aşırı yükleme kullanılarak yapılır.

İçinde öğesine çağrısı `Deposit` , `Account::Deposit` özel üye işlevini çağırır. Bu çağrı doğrudur çünkü `Account::Deposit` bir üye işlevi ve sınıfının özel üyelerine erişimi vardır.

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

[İşlevler (C++)](../cpp/functions-cpp.md)
