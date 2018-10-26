---
title: İşlev aşırı yüklemesi | Microsoft Docs
ms.custom: ''
ms.date: 1/25/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- function overloading [C++], about function overloading
- function overloading
- declaring functions [C++], overloading
ms.assetid: 3c9884cb-1d5e-42e8-9a49-6f46141f929e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d942e2c5bca7d86e66cb579de1cbe946cb9f5f6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50081501"
---
# <a name="function-overloading"></a>İşlev Aşırı Yüklemesi

C++, aynı kapsamda aynı ada sahip birden fazla işlevin belirtilmesini sağlar. Bunlar adlandırılır *aşırı* işlevleri. Aşırı yüklenmiş İşlevler, işlev için bağımsız değişken sayısı ve türleri bağlı olarak farklı semantikler sağlamak etkinleştirin.

Örneğin, bir `print` alan işlev bir `std::string` bağımsız değişken türünde bir bağımsız değişken birden çok farklı görevleri gerçekleştirebileceğiniz **çift**. Aşırı yükleme kaydeder, adları gibi kullanmak zorunda kalmaktan `print_string` veya `print_double`. Derleme zamanında derleyici, çağıran tarafından geçirilen bağımsız değişken türünü kullanmak için hangi aşırı yüklemenin göre seçer.  Eğer `print(42.0)` sonra `void print(double d)` işlevi çağrılacak. Eğer `print("hello world")` sonra `void print(std::string)` aşırı çağrılacak.

Üye işlevleri ve üye olmayan işlevleri hem aşırı yüklenebilir. Aşağıdaki tabloda, C++'nın aynı kapsamda aynı ana sahip işlev gruplarını birbirinden ayırmak için işlev bildiriminin hangi bölümlerini kullandığını gösterir.

### <a name="overloading-considerations"></a>Aşırı Yükleme Hakkında Önemli Noktalar

|İşlev Bildirimi Öğesi|Aşırı yükleme için kullanılır mı?|
|----------------------------------|---------------------------|
|İşlevin dönüş türü|Hayır|
|Bağımsız değişkenlerin sayısı|Evet|
|Bağımsız değişkenlerin türü|Evet|
|Üç noktanın olması veya olmaması|Evet|
|Kullanım **typedef** adları|Hayır|
|Belirtilmemiş dizi sınırları|Hayır|
|**const** veya **geçici**|Evet, tüm işlevine uygulandığında|
|[ref niteleyicisi](#ref-qualifier)|Evet|

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

Varsayılan bağımsız değişken işlev türünün bir parçası olarak kabul edilmez. Bu nedenle, aşırı yüklenmiş işlev seçmede kullanılmaz. Yalnızca kendi varsayılan bağımsız değişkenlerinde farklı olan iki işlevde, aşırı yüklenmiş işlevler yerine birden çok tanım dikkate alınır.

Varsayılan bağımsız değişkenleri, aşırı yükleme işleçleri için verilemez.

## <a name="argument-matching"></a>Bağımsız Değişken Eşleştirme

Aşırı yüklenmiş işlevler için işlev bildirimleri işlev çağırısında sağlanan bağımsız değişkenler için geçerli kapsamdaki en iyi eşleşmeyi seçilir. Uygun bir işlev bulunursa, bu işlev çağrılır. Bu bağlamda "uygun" aşağıdakilerden birini gösterir:

- Tam bir eşleşme bulunamadı.

- Dönüştürmelerden gerçekleştirildi.

- Bir integral yükseltme gerçekleştirildi.

- İstenen bağımsız değişken türüne standart dönüştürme yok.

- Kullanıcı tanımlı dönüştürme (dönüştürme işleci veya Oluşturucu) istenen bağımsız değişken türü var.

- Üç nokta tarafından temsil edilen bağımsız değişken bulunamadı.

Derleyici işlevleri için her bağımsız değişken adayı kümesi oluşturur. Aday işlevleri konumda gerçek bağımsız değişken biçimsel bağımsız değişkenin türüne dönüştürülebilir işlevlerdir.

Her bağımsız değişkeni için "en iyi eşleşen işlevleri" bir dizi yerleşik olarak bulunur ve tüm kümelerinin kesişimi seçili işlevdir. Aşırı yükleme kesişmesi birden fazla işlev içeriyorsa, belirsiz ve bir hata oluşturur. Sonunda seçilen her zaman her bir işlev grubunda daha iyi bir eşleşme için en az bir bağımsız değişken işlevdir. (Hiçbir açık kazanan yoksa) durum bu değilse, işlev çağrısı bir hata oluşturur.

Aşağıdaki bildirimleri dikkate alın (işlevler işaretlenmiş `Variant 1`, `Variant 2`, ve `Variant 3`, kimliği'nde aşağıdaki tartışma için):

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

Önceki deyim, iki kümesi oluşturur:

|Kümesi 1: İlk bağımsız değişken türü basamağını aday işlevleri|Kümesi 2: Aday işlevleri Whose ikinci bağımsız değişkeni dönüştürülebilir türü **int**|
|--------------------------------------------------------------------------|-----------------------------------------------------------------------------------|
|Değişken 1|Değişken 1 (**int** dönüştürülebilir **uzun** standart bir dönüştürme kullanılarak)|
|Değişken 3||

İşlevler kümesi 2: hangi işlevleri var olan gerçek parametre türü biçimsel parametre türüne örtük dönüşümlere ve bu tür işlevleri arasında "gerçek parametre türü, biçimsel parametre türüne dönüştürme maliyeti" olduğu bir işlev yok en küçük.

Bu iki kümenin kesişimini değişken 1 ' dir. Belirsiz bir işleve örneğidir:

```cpp
F1 = Add( 3, 6 );
```

Önceki işlev çağrısı aşağıdaki oluşturur:

|Kümesi 1: Aday işlevleri, sahip ilk bağımsız değişken türü **int**|Kümesi 2: Aday işlevleri emin olan ikinci bağımsız değişken türü **int**|
|---------------------------------------------------------------------|----------------------------------------------------------------------|
|Değişken 2 (**int** dönüştürülebilir **uzun** standart bir dönüştürme kullanılarak)|Değişken 1 (**int** dönüştürülebilir **uzun** standart bir dönüştürme kullanılarak)|

Bu iki kümesi arasında kesişimi boş olduğunu unutmayın. Bu nedenle, derleyici bir hata iletisi oluşturur.

Bağımsız değişkeni bir işlev ile eşleşen *n* varsayılan bağımsız değişkenler olarak kabul edildiği *n*+ 1 ayrı İşlevler, her biri farklı sayıda bağımsız değişken.

Joker karakter üç nokta (...) görür; Bu, herhangi bir gerçek bağımsız değişken ile eşleşir. Son derece dikkatli olunmalıdır ile aşırı yüklenmiş işlev kümeleriniz tasarlamayın varsa bu birçok belirsiz kümelerine neden olabilir.

> [!NOTE]
>  Belirsizlik işlevlerin aşırı yüklenmiş işlev çağrısı karşılaşılanaa kadar belirlenemiyor. Bu noktada, kümeleri işlev çağrısındaki her bağımsız değişkeni oluşturulur ve anlaşılır bir aşırı bulunup bulunmadığını belirleyebilirsiniz. Bu, bunlar belirli işlev çağrısına göre evoked kadar belirsizlikleri kodunuzda kalabileceği anlamına gelir.

## <a name="argument-type-differences"></a>Bağımsız Değişken Türü Farkları

Aşırı yüklenmiş işlevler, farklı başlatıcıları olan bağımsız değişken türlerini ayırt eder. Bu nedenle, belirli türden bir bağımsız değişken ve bu türe yapılan bir başvuru, aşırı yükleme amaçları için aynı olarak kabul edilir. Aynı başlatıcıları aldıkları için aynı olarak kabul edilirler. Örneğin `max( double, double )`, `max( double &, double & )` ile aynı olarak kabul edilir. Böyle iki işlevin bildirilmesi bir hataya neden olur.

Aynı nedenden dolayı bağımsız değişkenleri tarafından değiştirilen türün işlev **const** veya **geçici** temel türden farklı aşırı yükleme amaçları için değerlendirilir.

Ancak işlev aşırı yükleme mekanizması tarafından nitelendirilen başvuruları arasında ayrım yapabilme kolaylığı **const** ve **geçici** ve temel tür referansı. Bu, aşağıdaki gibi kodlara imkan tanır:

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

### <a name="output"></a>Çıkış

```Output
Over default constructor
Over&
Over default constructor
const Over&
Over default constructor
volatile Over&
```

İşaretçileri **const** ve **geçici** nesneleri ayrıca değerlendirilir temel türün işaretçilerinden farklı aşırı yükleme amaçları için.

## <a name="argument-matching-and-conversions"></a>Bağımsız değişken eşleme ve dönüşümleri

Derleyici, gerçek bağımsız değişkenler İşlev bildirimlerinde bağımsız karşı eşleşecek şekilde çalıştığında, tam eşleşme bulunamazsa, doğru türü elde etmek için standart veya kullanıcı tanımlı dönüştürmeler sağlayabilirsiniz. Bu kurallar tabi dönüştürmeler uygulamasıdır:

- Dizileri içeren kullanıcı tanımlı dönüştürme birden fazla dönüştürülme dikkate alınmaz.

- Ara dönüştürmeler kaldırarak kısalttık dönüştürmeler dönüştürülmelerini dikkate alınmaz.

Dönüştürme, sonuç dizi sırası eşleştirme en iyi varsa çağrılır. Türünde bir nesneyi dönüştürmek için birkaç şekilde **int** türüne **işaretsiz uzun** standart dönüştürmeler kullanarak (açıklanan [standart dönüştürmeler](../cpp/standard-conversions.md)):

- Dönüştürmek **int** için **uzun** ve sonra **uzun** için **işaretsiz uzun**.

- Dönüştürmek **int** için **işaretsiz uzun**.

İstenen hedef, başarır rağmen ilk dizi sırası eşleştirme en iyi değildir — daha kısa bir dizisi yok.

Aşağıdaki tabloda, dönüştürme, en iyi eşleşen hangi sırasıdır belirleme sınırlı etkisi Önemsiz dönüştürmeler, adlı bir grubu gösterir. Basit dönüştürme sırası, tercih ettiğiniz etkileyen örnekleri aşağıdaki tablonun listede açıklanmıştır.

### <a name="trivial-conversions"></a>Basit dönüştürme

|Türünden dönüştürme|Türüne dönüştürün|
|-----------------------|---------------------|
|*tür adı*|*tür adı* **&**|
|*tür adı* **&**|*tür adı*|
|*tür adı* **]**|*tür adı\**|
|*tür adı* **(** *bağımsız değişken listesi* **)**|**(**  *\*tür adı* **) (** *bağımsız değişken listesi* **)**|
|*tür adı*|**const** *tür adı*|
|*tür adı*|**volatile** *tür adı*|
|*tür adı\**|**const** *tür adı\**|
|*tür adı\**|**volatile** *tür adı\**|

Dönüştürmeleri denenmez sırası aşağıdaki gibidir:

1. Tam eşleşme. Hangi işlev çağrılır ve türleri işlev prototipi içinde bildirilen türler arasında bir tam eşleşme her zaman en iyi eşleşmedir. Önemsiz dönüştürmeler dizileri tam eşleşme sınıflandırılır. Ancak, bu dönüştürmeler yapmayın dizileri dönüştürme dizileri iyi kabul edilir:

   - İşaretçiden işaretçiye için **const** (`type` <strong>\*</strong> için **const** `type` <strong>\*</strong> ).

   - İşaretçiden işaretçiye için **geçici** (`type` <strong>\*</strong> için **geçici** `type` <strong>\*</strong>).

   - Başvuru için başvurusundan **const** (`type` **&** için **const** `type` **&**).

   - Başvuru için başvurusundan **geçici** (`type` **&** için **geçici** `type` **&**).

1. Promosyon kullanarak eşleştirin. Yalnızca integral yükseltmeler, dönüşümlerse içeren tam bir eşleşme olarak sınıflandırılan değil herhangi bir dizisi **float** için **çift**, ve önemsiz dönüştürmeler promosyonlar kullanarak bir eşleşme olarak sınıflandırılmış. Kadar iyi bir eşleşme rağmen tam bir eşleşme olarak promosyonlar kullanarak bir eşleşme standart dönüştürmeler kullanarak bir eşleşme iyidir.

1. Standart dönüştürmeler kullanarak eşleştirin. Tam bir eşleşme veya yalnızca standart dönüştürmeler veya önemsiz dönüştürmeler içeren promosyonlar kullanarak bir eşleşme olarak sınıflandırılan değil herhangi bir dizisi, standart dönüştürmeler kullanarak bir eşleşme olarak sınıflandırılır. Bu kategori, aşağıdaki kurallar uygulanır:

   - Bir doğrudan veya dolaylı taban sınıfı işaretçisini bir türetilmiş sınıf işaretçisine dönüştürme için dönüştürme tercih `void *` veya `const void *`.

   - Bir taban sınıfı işaretçisini bir türetilmiş sınıf işaretçisine dönüştürme daha yakın temel sınıfı için doğrudan temel sınıf olan daha iyi bir eşleşme üretir. Aşağıdaki şekilde gösterilen sınıf hiyerarşisini olduğunu varsayın.

![Tercih edilen dönüştürmeler](../cpp/media/vc391t1.gif "vc391T1") grafik gösteren tercih edilen dönüştürmeler

Türünden dönüştürme `D*` türüne `C*` türünden dönüştürme için tercih edilir `D*` türüne `B*`. Benzer şekilde, türünden dönüştürme `D*` türüne `B*` türünden dönüştürme için tercih edilir `D*` türüne `A*`.

Bu aynı kural için başvuru dönüşümleri uygular. Türünden dönüştürme `D&` türüne `C&` türünden dönüştürme için tercih edilir `D&` türüne `B&`ve benzeri.

Bu aynı kural için işaretçi-üye dönüşümleri uygular. Türünden dönüştürme `T D::*` türüne `T C::*` türünden dönüştürme için tercih edilir `T D::*` türüne `T B::*`ve benzeri (burada `T` üye türü).

Önceki kural türetme yalnızca belirli bir yol geçerlidir. Aşağıdaki şekilde gösterilen grafiğe göz önünde bulundurun.

![Çoklu&#45;tercih edilen dönüştürmeler gösteren devralma](../cpp/media/vc391t2.gif "vc391T2") birden çok devralma grafiği gösteren tercih edilen dönüştürmeler

Türünden dönüştürme `C*` türüne `B*` türünden dönüştürme için tercih edilir `C*` türüne `A*`. Aynı yolda olduklarını nedenidir ve `B*` daha yakındır. Ancak, türünden dönüştürme `C*` türüne `D*` türüne dönüştürme tercih değil `A*`; yoktur tercih yoktur çünkü dönüştürmeler farklı yolları izleyin.

1. Kullanıcı tanımlı dönüşümler ile eşleştirin. Bu sıra tam bir eşleşme, promosyonlar kullanarak bir eşleşme veya standart dönüştürmeler kullanarak bir eşleşme sınıflandırılamaz. Sıra, yalnızca kullanıcı tanımlı dönüştürmeler, standart dönüştürmeler veya kullanıcı tanımlı dönüşümler ile bir eşleşme olarak sınıflandırılması Önemsiz dönüştürmeler içermelidir. Kullanıcı tanımlı dönüşümler ile bir eşleşme, üç nokta ile eşleşmeyi ancak kadar iyi bir eşleşme ile standart dönüştürmeler bir eşleşme olarak daha iyi bir eşleşme olarak kabul edilir.

1. Üç nokta ile eşleşir. Üç nokta bildiriminde eşleşen tüm dizisi, üç nokta ile bir eşleşme olarak sınıflandırılır. Bu, zayıf eşleşme olarak değerlendirilir.

Herhangi bir yerleşik bir yükseltmeyi veya dönüştürme varsa, kullanıcı tanımlı dönüşümler uygulanır. Bu dönüştürmeler eşleşen bağımsız değişken türünü temel alınarak seçilir. Aşağıdaki kodu göz önünde bulundurun:

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

Sınıfı için kullanılabilen kullanıcı tanımlı dönüşümler `UDC` türünden olan **int** ve türü **uzun**. Bu nedenle, derleyici eşleştirilen nesne türü için dönüştürme göz önünde bulundurur: `UDC`. Dönüştürme **int** var ve seçili.

Bağımsız değişken eşleştirme işlemi sırasında hem bağımsız değişken hem de kullanıcı tanımlı bir dönüştürmenin sonucu için standart dönüştürmeler uygulanabilir. Bu nedenle, aşağıdaki kod çalışır:

```cpp
void LogToFile( long l );
...
UDC udc;
LogToFile( udc );
```

Yukarıdaki örnekte, kullanıcı tanımlı dönüştürme **long işleci**, dönüştürmek için çağrılan `udc` türüne **uzun**. Yazmak için kullanıcı tanımlı dönüştürme, **uzun** olsaydı tanımlanmış dönüştürme gibi proceeded: türü `UDC` türüne dönüştürülmüş **int** kullanarak kullanıcı tanımlı dönüştürme. Ardından türüne standart dönüştürme **int** türüne **uzun** bağımsız değişken bildiriminde eşleştirilecek uygulanmış.

Herhangi bir kullanıcı tanımlı dönüşümler eşleştirilmesi bağımsız değişken için standart dönüştürmeler en iyi eşleşmeyi değerlendirirken kullanılmaz. Birden fazla aday işlevi kullanıcı tanımlı bir dönüştürme gerekli olsa bile bu geçerlidir; Böyle bir durumda işlevleri eşit olarak kabul edilir. Örneğin:

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

Her iki sürümü `Func` türü dönüştürmek için bir kullanıcı tanımlı dönüştürme gerektiren **int** sınıf türü bağımsız değişkeni. Olası dönüştürmeler şunlardır:

- Türünden dönüştürme **int** türüne `UDC1` (kullanıcı tanımlı dönüştürme).

- Türünden dönüştürme **int** türüne **uzun**; ardından türüne dönüştürme `UDC2` (iki aşamalı dönüştürme).

Bu ikinci kullanıcı tanımlı dönüştürme yanı sıra, standart bir dönüşüm gerektiriyor olsa da, iki dönüştürmeler yine de eşit olarak kabul edilir.

> [!NOTE]
>  Kullanıcı tanımlı dönüşümler dönüştürme oluşturma veya dönüştürme başlatma (dönüştürme işlevi) tarafından kabul edilir. Her iki yöntem de en iyi eşleşmeyi değerlendirirken eşit olarak kabul edilir.

## <a name="argument-matching-and-the-this-pointer"></a>Bağımsız değişken eşleştirme ve this işaretçisi

Sınıf üyesi işlevleri kabul edilir farklı olarak bildirilip bağlı olarak **statik**. Statik olmayan işlevler sağlayan örtük bağımsız değişken olduğundan **bu** işaretçisi, statik olmayan işlevlerin statik İşlevler'den daha fazla bir bağımsız değişkene sahip olarak kabul edilir; Aksi halde aynı şekilde beyan edildiklerine bağlıdır.

Bu statik olmayan üye işlevleri örtük **bu** işaretçi eşleşen üzerinden işlevi çağrılan nesne türü veya aşırı yüklenmiş işleçler için ilk bağımsız değişken nesne eşleşmesini gerektirir. işleç uygulanıyor. (Aşırı yüklenmiş işleçler hakkında daha fazla bilgi için bkz: [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md).)

Aşırı yüklenmiş işlevlerdeki diğer bağımsız değişkenlerin aksine, hiçbir geçici nesne kullanıma sunulmaz ve hiçbir dönüştürme çalışılırken denenme **bu** işaretçi bağımsız değişkeni.

Zaman `->` üye seçme işleci bir sınıfın üye işlevine erişmek için kullanılan `class_name`, **bu** işaretçi bağımsız değişkeni bir tür olan `class_name * const`. Üyeleri olarak bildirilmişse **const** veya **geçici**, türler `const class_name * const` ve `volatile class_name * const`sırasıyla.

`.` üye seçme işleci, örtük `&` (adres) işlecinin nesne adının önüne eklenmesi dışında tamamen aynı şekilde çalışır. Aşağıdaki örnekte, bunun nasıl çalıştığı gösterilmektedir:

```cpp
// Expression encountered in code
obj.name

// How the compiler treats it
(&obj)->name
```

Sol işleneni `->*` ve `.*` (üye işaretçisi) işleçleri aynı şekilde ele alınır `.` ve `->` göre bağımsız değişken eşleştirme (üye seçme) işleçleri.

## <a name="ref-qualifiers"></a> Üye işlevlerin ref tanımlayıcıları

Başvuru niteleyicileri olanaklı hale getirir olup olmadığı için tarafından işaret edilen nesne göndermemeniz bir üye işlev aşırı yükleme **bu** rvalue veya bir lvalue.  Bu özellik senaryolarda gereksiz kopyalama işlemleri önlemek için işaretçi verilere erişim sağlamak seçtiğiniz kullanılabilir. Örneğin, sınıf varsayın `C` oluşturucusuna bazı verileri başlatır ve üye işlevinde, verilerin bir kopyasını döndürür `get_data()`. Bir nesne türü ise `C` derleyici seçecektir sonra edilmek üzere olan bir rvalue olduğunu `get_data() &&` kopyalamak yerine aşırı yükleme, hangi verileri taşır.

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

Birkaç kısıtlama, kabul edilebilir bir aşırı yüklenmiş işlevler kümesi yöneten:

- Her iki işlev aşırı yüklenmiş işlevler kümesinde farklı bağımsız değişken listeleri olması gerekir.

- Tek başına dönüş türüne bağlı olarak aynı tür bağımsız değişken listeleriyle işlevler aşırı yüklemesi bir hata var.

     **Microsoft'a özgü**

Aşırı yükleyebilirler **new işleci** yalnızca temeline göre dönüş türü — özellikle, belirtilen bellek modeli değiştiricisi göndermemeniz.

**END Microsoft özgü**

- Üye işlevleri yalnızca bir statik olan ve diğer statik dışı göndermemeniz aşırı yüklenemez.

- **TypeDef** bildirimleri yeni türleri tanımlamaz; bunlar varolan türleri için eş anlamlı sözcükler tanıtır. Aşırı yüklerken mekanizması etkilemez. Aşağıdaki kodu göz önünde bulundurun:

    ```cpp
    typedef char * PSTR;

    void Print( char *szToPrint );
    void Print( PSTR szToPrint );
    ```

   Önceki iki işlev aynı bağımsız değişken listeleri vardır. `PSTR` tür eşanlamlıdır `char *`. Üye kapsamda Bu kod bir hata oluşturur.

- Numaralandırılmış türler farklı türler ve aşırı yüklenmiş işlevler arasında ayrım yapmak için kullanılabilir.

- Türü "array" ve "işaretçisi" aşırı yüklenmiş işlevler arasında ayrım amacıyla aynı olarak kabul edilir. Bu, yalnızca tek dimensioned diziler için geçerlidir. Bu nedenle, aşağıdaki işlevleri çakışma aşırı ve bir hata iletisi oluşturur:

    ```cpp
    void Print( char *szToPrint );
    void Print( char szToPrint[] );
    ```

   Birden çok kez dimensioned diziler için ikinci ve sonraki tüm boyutlar, türün bir parçası olarak kabul edilir. Bu nedenle, bunlar aşırı yüklenmiş işlevler arasında ayrım içinde kullanılır:

    ```cpp
    void Print( char szToPrint[] );
    void Print( char szToPrint[][7] );
    void Print( char szToPrint[][9][42] );
    ```

## <a name="overloading-overriding-and-hiding"></a>Aşırı yüklemesi, geçersiz kılma ve gizleme

Her iki işlev bildirimleri aynı kapsamda aynı adın, aynı işlevin veya aşırı iki ayrı işlevler başvurabilir. Bağımsız değişken listeleri (önceki bölümde açıklandığı gibi) bağımsız değişken eşdeğer türlerinin bildirimlerini içeren, aynı işleve işlev bildirimlerine bakın. Aksi takdirde aşırı yüklemesi kullanarak seçili olan iki farklı işlevleri bakın.

Sınıf kapsamı kesinlikle gözlemlenen; Bu nedenle, bir temel sınıfta bildirilen bir işlevi bir işlev ile aynı kapsamda türetilmiş sınıf içinde bildirilmedi. Bir işlev türetilen bir sınıfta türetilmiş sınıf işlevi taban sınıfında sanal işlevi olarak aynı ada sahip olarak tanımlanıp tanımlanmadığını *geçersiz kılmalar* temel sınıf işlevi. Daha fazla bilgi için [sanal işlevler](../cpp/virtual-functions.md).

Temel sınıf işlevini 'virtual' olarak bildirilmedi ardından türetilmiş sınıf işlevi belirtilmektedir *Gizle* bu. Hem geçersiz kılma ve gizleme aşırı yüklemesini farklıdır.

Blok kapsamı kesinlikle gözlemlenen; Bu nedenle, dosya kapsamı içinde bildirilen bir işlevi bir işlev ile aynı kapsamda yerel olarak bildirilmedi. Yerel olarak bildirilen bir işleve dosya kapsamı içinde bildirilen bir işlevi olarak aynı ada sahip, yerel olarak bildirilen işlev aşırı yüklemesi neden yerine dosya kapsamlı işlevi gizler. Örneğin:

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

Yukarıdaki kod, iki işlev tanımları gösterir `func`. Türünde bir bağımsız değişken tanımı `char *` için yerel `main` nedeniyle **extern** deyimi. Bu nedenle, türünde bir bağımsız değişken tanımı **int** gizlidir ve ilk çağrıda `func` hata.

Aşırı yüklü üye işlevler için işlev farklı sürümlerini farklı erişim ayrıcalığı verilebilir. Bunlar, kapsayan sınıf kapsamı içinde olarak kabul edilir ve bu nedenle aşırı yüklenmiş işlevler şunlardır. Aşağıdaki kodu düşünün üye işlevi `Deposit` aşırı yüklendi; bir sürüm genel, diğer, özel.

Bu örnek amacı sağlamaktır bir `Account` sınıfı içinde doğru parolayı mevduatlarını gerçekleştirmek için gereklidir. Bu aşırı yüklemesi kullanarak gerçekleştirilir.

Unutmayın çağrısı `Deposit` içinde `Account::Deposit` özel üye işlevini çağırır. Bu çağrı doğru olduğundan `Account::Deposit` bir üye işlevidir ve bu nedenle özel üyeleri sınıfın erişebilir.

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

[işlevler [C++]](../cpp/functions-cpp.md)