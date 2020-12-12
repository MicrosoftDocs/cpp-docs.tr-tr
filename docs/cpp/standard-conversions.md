---
description: Daha fazla bilgi için bkz. Standart dönüştürmeler
title: Standart dönüşümler
ms.date: 10/02/2019
helpviewer_keywords:
- standard conversions, categories of
- L-values [C++]
- conversions, standard
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
ms.openlocfilehash: cfebc861fca1ccf8119c6055b37f112df7d4dca0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318045"
---
# <a name="standard-conversions"></a>Standart dönüşümler

C++ dili, temel türleri arasındaki dönüştürmeleri tanımlar. Ayrıca işaretçi, başvuru ve işaretçiden üyeye türetilmiş türler için dönüşümler tanımlar. Bu dönüşümler *Standart dönüşümler* olarak adlandırılır.

Bu bölümde aşağıdaki standart dönüşümler ele alınmaktadır:

- Integral yükseltmeler

- Integral dönüştürmeleri

- Kayan dönüşümler

- Kayan ve tam sayı dönüştürmeleri

- Aritmetik dönüştürmeler

- İşaretçi Dönüştürmeler

- Başvuru dönüştürmeleri

- İşaretçiden üyeye dönüştürmeleri

  > [!NOTE]
  > Kullanıcı tanımlı türler kendi dönüştürmelerini belirtebilir. Kullanıcı tanımlı türlerin dönüştürülmesi [oluşturucular](../cpp/constructors-cpp.md) ve [dönüştürmelerde](../cpp/user-defined-type-conversions-cpp.md)ele alınmıştır.

Aşağıdaki kod dönüştürmeye neden olur (Bu örnekte, integral promosyonları):

```cpp
long  long_num1, long_num2;
int   int_num;

// int_num promoted to type long prior to assignment.
long_num1 = int_num;

// int_num promoted to type long prior to multiplication.
long_num2 = int_num * long_num2;
```

Bir dönüştürmenin sonucu yalnızca bir başvuru türü üretirse bir l değeridir. Örneğin, olarak belirtilen kullanıcı tanımlı bir dönüştürme `operator int&()` bir başvuru döndürür ve bir l değeri olur. Ancak, olarak belirtilen bir dönüştürme bir `operator int()` nesnesi döndürür ve bir l değeri değildir.

## <a name="integral-promotions"></a>Integral yükseltmeler

İntegral türündeki nesneler, daha büyük bir değer kümesini temsil eden bir tür olan başka bir geniş integral türüne dönüştürülebilir. Bu dönüştürme türü, *integral yükseltme* olarak adlandırılır. İntegral yükseltme ile, başka bir integral türünün kullanılabileceği her yerde aşağıdaki türleri bir ifadede kullanabilirsiniz:

- Ve türündeki nesneler, sabit değerler ve sabitler **`char`****`short int`**

- Numaralandırma türleri

- **`int`** bit alanları

- Numaralandırıcılar

Yükseltmeden sonraki değerin, yükseltmeden önceki değerle aynı olması garanti edildikten sonra C++ yükseltmeleri "değer-koruma" olur. Değer koruma promosyonları ' nda, daha kısa integral türündeki nesneler (örneğin, bit alanları veya tür nesneleri **`char`** ), **`int`** **`int`** özgün türün tam aralığını temsil ediyorsa türüne yükseltilir. **`int`** Değerlerin tam aralığını temsil etemiyorum, nesne türüne yükseltilir **`unsigned int`** .  Bu strateji standart C tarafından kullanılan bir ile aynı olsa da, değer koruma dönüştürmelerinde nesnenin "signedyeti" yoktur.

Değer korumalı yükseltmeler ve işaretli durumu koruyan yükseltmeler normalde aynı sonuçları verir. Ancak, yükseltilen nesne şöyle görünüyorsa farklı sonuçlar üretebilirler:

- ,,,,, `/` `%` `/=` `%=` `<` `<=` , `>` , Veya işleneni `>=`

   Bu işleçler sonucu belirlemek için işareti kullanırlar. Değer koruma ve oturum koruma yükseltmeleri, bu işlenenlere uygulandığında farklı sonuçlar üretir.

- Veya sol işleneni `>>``>>=`

   Bu işleçler, imzalanmış ve işaretsiz miktarları bir vardiya işleminde farklı şekilde işler. İşaretli miktarlar için, bir sağ kaydırma işlemi, işaret biti konumlarına, işaretsiz miktarlar sıfır doldurulurken, işaret bitini bir arada yayar.

- Aşırı yüklenmiş bir işlevin bağımsız değişkeni veya aşırı yüklenmiş bir işlecin işleneni, bağımsız değişken eşleştirme için işlenen türünün signedliğine bağlıdır. Aşırı yüklenmiş işleçleri tanımlama hakkında daha fazla bilgi için bkz. [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md).

## <a name="integral-conversions"></a>Integral dönüştürmeleri

*İntegral dönüştürmeleri* integral türleri arasındaki Dönüştürmelere sahiptir. İntegral türleri **`char`** , **`short`** (veya **`short int`** ),, **`int`** **`long`** ve **`long long`** . Bu türler veya ile nitelenmiş olabilir **`signed`** **`unsigned`** ve **`unsigned`** için kısayol olarak kullanılabilir **`unsigned int`** .

### <a name="signed-to-unsigned"></a>İmzasız imzalı

İşaretli integral türlerindeki nesneler, ilgili işaretsiz türlere dönüştürülebilir. Bu dönüşümler gerçekleştiğinde, gerçek bit desenler değişmez. Ancak, verilerin yorumu değişir. Bu kodu göz önünde bulundurun:

```cpp
#include <iostream>

using namespace std;
int main()
{
    short  i = -3;
    unsigned short u;

    cout << (u = i) << "\n";
}
// Output: 65533
```

Yukarıdaki örnekte, bir **`signed short`** , `i` tanımlanır ve negatif bir sayı olarak başlatılır. İfade, `(u = i)` `i` atamasından önce öğesine dönüştürülmesine neden olur **`unsigned short`** `u` .

### <a name="unsigned-to-signed"></a>İmzasız imzalı

İşaretsiz integral türlerindeki nesneler, ilgili işaretli türlere dönüştürülebilir. Ancak, işaretsiz değer imzalı türün gösterilemeyen aralığın dışındaysa, aşağıdaki örnekte gösterildiği gibi sonuç doğru değere sahip olmayacaktır:

```cpp
#include <iostream>

using namespace std;
int main()
{
short  i;
unsigned short u = 65533;

cout << (i = u) << "\n";
}
//Output: -3
```

Önceki örnekte, `u` **`unsigned short`** ifadeyi değerlendirmek için işaretli bir miktara dönüştürülmesi gereken bir integral nesnesidir `(i = u)` . Değeri bir içinde doğru şekilde temsil edilemediğinden **`signed short`** , veriler gösterildiği gibi yanlış yorumlanır.

## <a name="floating-point-conversions"></a>Kayan nokta dönüştürmeleri

Kayan türden bir nesne güvenle daha kesin bir kayan türe dönüştürülebilir — diğer bir deyişle, dönüştürme hiçbir anlam kaybına neden olmaz. Örneğin, ' den ' e veya türünden ' ye dönüştürme **`float`** **`double`** **`double`** **`long double`** güvenlidir ve değer değiştirilmez.

Kayan türden bir nesne, bu tür tarafından bir Aralık gösterilebilir tablo ise daha az kesin bir türe de dönüştürülebilir. (Kayan türlerin aralıkları için bkz. [kayan sınırlar](../cpp/floating-limits.md) .) Özgün değer tam olarak gösterilemeyen tablo değilse, bir sonraki daha yüksek veya daha düşük gösterilemeyen değere dönüştürülebilir. Bu değer yoksa sonuç tanımsızdır. Aşağıdaki örneği inceleyin:

```cpp
cout << (float)1E300 << endl;
```

Türe göre maksimum değer gösterilebilir tablo, **`float`** 3.402823466 E38 — 1E300 ' dan çok daha küçük bir sayıdır. Bu nedenle, sayı sonsuz olarak dönüştürülür ve sonuç "INF" dir.

## <a name="conversions-between-integral-and-floating-point-types"></a>İntegral ve kayan nokta türleri arasındaki dönüşümler

Belirli ifadeler, kayan türde nesneleri integral türlerine dönüştürebilirler veya tam tersi olabilir. İntegral türündeki bir nesne kayan bir türe dönüştürüldüğünde ve özgün değer tam olarak gösterilemeyen şekilde görüntülenmiyorsa, sonuç bir sonraki daha yüksek veya daha düşük bir sonraki değer olarak gösterilebilir.

Kayan türden bir nesne integral türüne dönüştürüldüğünde kesirli bölüm *kesilir* veya sıfıra yuvarlanır. 1,3 gibi bir sayı 1 ' e dönüştürülüp-1,3-1 ' e dönüştürülür. Kesilen değer en yüksek gösterilemeyen değerden yüksekse veya en düşük gösterilemeyen değerden düşükse, sonuç tanımsızdır.

## <a name="arithmetic-conversions"></a>Aritmetik dönüştürmeler

Birçok ikili işleç ( [ikili işleçlere sahip ifadelerde](../cpp/expressions-with-binary-operators.md)açıklanmıştır) işlenenlerin dönüştürmelerine neden olur ve aynı şekilde sonuç verir. Bu işleçlerin dönüşümlerine neden olan dönüşümler, *Olağan aritmetik dönüştürmeler* olarak adlandırılır. Farklı yerel türlerine sahip işlenenlerin aritmetik dönüştürmeleri, aşağıdaki tabloda gösterildiği gibi yapılır. Typedef türleri, temel yerel türlerine göre davranır.

### <a name="conditions-for-type-conversion"></a>Tür dönüştürme koşulları

|Koşullar karşılandı|Dönüştürme|
|--------------------|----------------|
|İşlenen türü **`long double`** .|Diğer işlenen türüne dönüştürüldü **`long double`** .|
|Önceki koşul karşılanmadı ve iki işlenen de türde **`double`** .|Diğer işlenen türüne dönüştürüldü **`double`** .|
|Önceki koşulların karşılanmamaları ve her iki işlenenin de türü **`float`** .|Diğer işlenen türüne dönüştürüldü **`float`** .|
|Önceki koşullar karşılanmamıştır (işlenenlerden hiçbiri kayan türlerden değil).|İşlenenler integral promosyonları aşağıdaki gibi alır:<br /><br />-Her iki işlenen de tür ise **`unsigned long`** , diğer işlenen türüne dönüştürülür **`unsigned long`** .<br />-Önceki koşul karşılanmazsa ve iki işlenenin türü **`long`** ve diğeri türü ise, **`unsigned int`** her iki işlenen de türüne dönüştürülür **`unsigned long`** .<br />-Önceki iki koşul karşılanmazsa ve iki işlenenin türü ise **`long`** , diğer işlenen türüne dönüştürülür **`long`** .<br />-Önceki üç koşul karşılanmazsa ve iki işlenenin türü ise **`unsigned int`** , diğer işlenen türüne dönüştürülür **`unsigned int`** .<br />-Önceki koşulların hiçbiri karşılanmazsa her iki işlenen de türüne dönüştürülür **`int`** .|

Aşağıdaki kodda, tabloda açıklanan dönüştürme kuralları gösterilmektedir:

```cpp
double dVal;
float fVal;
int iVal;
unsigned long ulVal;

int main() {
   // iVal converted to unsigned long
   // result of multiplication converted to double
   dVal = iVal * ulVal;

   // ulVal converted to float
   // result of addition converted to double
   dVal = ulVal + fVal;
}
```

Yukarıdaki örnekte bulunan ilk deyim, iki integral türü olan `iVal` ve `ulVal`'ın çarpımını göstermektedir. Koşul, hiçbir işlenenin kayan türde olmadığı ve bir işlenenin türü olduğu durumdur **`unsigned int`** . Bu nedenle, diğer işlenen `iVal` türüne dönüştürülür **`unsigned int`** . Sonuç daha sonra öğesine atanır `dVal` . Burada karşılanan koşul bir işlenenin türüdür **`double`** , bu nedenle **`unsigned int`** çarpma sonucu, türe dönüştürülür **`double`** .

Yukarıdaki örnekteki ikinci ifadede, ve integral türünün yanı sıra bir **`float`** integral türü gösterilmektedir: `fVal` ve `ulVal` . `ulVal`Değişken türüne dönüştürüldü **`float`** (tablodaki üçüncü koşul). Eklemenin sonucu türüne dönüştürülür **`double`** (tablodaki ikinci koşul) ve öğesine atanır `dVal` .

## <a name="pointer-conversions"></a>İşaretçi Dönüştürmeler

İşaretçiler atama, başlatma, karşılaştırma ve diğer ifadeler sırasında dönüştürülebilir.

### <a name="pointer-to-classes"></a>Sınıfların işaretçisi

Bir sınıfa yönelik işaretçinin, temel sınıfa olan işaretçiye dönüştürülebileceği iki durum vardır.

İlk durum, belirtilen temel sınıfa erişilebilir olduğu ve dönüştürmenin belirsiz olduğu durumdur. Belirsiz temel sınıf başvuruları hakkında daha fazla bilgi için bkz. [birden çok temel sınıf](../cpp/multiple-base-classes.md).

Temel bir sınıfa erişilebilir olup olmadığı, türetmede kullanılan devralmanın türüne bağlıdır. Aşağıdaki şekilde gösterilen devralmayı göz önünde bulundurun.

![Temel&#45;sınıfı erişilebilirliğini gösteren devralma grafiği](../cpp/media/vc38xa1.gif "Temel&#45;sınıfı erişilebilirliğini gösteren devralma grafiği") <br/>
Base-Class erişilebilirliği gösterimi için devralma grafiği

Aşağıdaki tabloda, şekilde gösterildiği durumlar için temel sınıf erişilebilirliği gösterilmektedir.

|Işlevin türü|Mede|Dönüştürme<br /><br /> B * \* geçerli mi?|
|----------------------|----------------|-------------------------------------------|
|Dış (sınıf kapsamlı değil) işlevi|Özel|Hayır|
||Korumalı|Hayır|
||Genel|Evet|
|B üye işlevi (B kapsamında)|Özel|Evet|
||Korumalı|Evet|
||Genel|Evet|
|C üye işlevi (C kapsamında)|Özel|Hayır|
||Korumalı|Evet|
||Genel|Evet|

Bir sınıfa yönelik işaretçinin bir taban sınıfına bir işaretçiye dönüştürülebileceği ikinci durum, açık bir tür dönüştürmesi kullandığınız durumdur. Açık tür dönüştürmeleri hakkında daha fazla bilgi için bkz. [Açık tür dönüştürme işleci](explicit-type-conversion-operator-parens.md).

Bu tür bir dönüştürmenin sonucu, nesnenin temel sınıf tarafından tamamen tanımlanan bölümü olan *alt nesne için* bir işaretçidir.

Aşağıdaki kod, `A` ve `B` ' `B` den türetildiği iki sınıfı tanımlar `A` . (Devralma hakkında daha fazla bilgi için bkz. [türetilmiş sınıflar](../cpp/inheritance-cpp.md).) Daha sonra `bObject` , türü bir nesne `B` ve `pA` nesneyi işaret eden iki işaretçi (ve `pB` ) tanımlar.

```cpp
// C2039 expected
class A
{
public:
    int AComponent;
    int AMemberFunc();
};

class B : public A
{
public:
    int BComponent;
    int BMemberFunc();
};
int main()
{
   B bObject;
   A *pA = &bObject;
   B *pB = &bObject;

   pA->AMemberFunc();   // OK in class A
   pB->AMemberFunc();   // OK: inherited from class A
   pA->BMemberFunc();   // Error: not in class A
}
```

İşaretçi `pA` türü `A *` , anlamı "türünde bir nesne işaretçisi" olarak yorumlanabilen türdür `A` . `bObject`(Ve gibi) üyeleri `BComponent` , `BMemberFunc` yazmak için benzersizdir `B` ve bu nedenle ile erişilemez `pA` . `pA`İşaretçi yalnızca sınıfında tanımlanmış olan nesnenin özelliklerine (üye işlevleri ve veriler) erişim sağlar `A` .

### <a name="pointer-to-function"></a>İşlev işaretçisi

`void *`Tür, `void *` Bu işaretçiyi tutacak kadar büyükse, bir işlev işaretçisi türüne dönüştürülebilir.

### <a name="pointer-to-void"></a>Void işaretçisi

Türe işaretçiler **`void`** , diğer tüm tür işaretçilerine dönüştürülebilir, ancak yalnızca açık tür saçılması (C 'nin aksine). Herhangi bir türe yönelik bir işaretçi, örtük olarak türüne bir işaretçiye dönüştürülebilir **`void`** . Bir türün tamamlanmamış bir nesnesine yönelik bir işaretçi, **`void`** (örtük) ve geri (açıkça) işaretçisine dönüştürülebilir. Bu tür bir dönüştürmenin sonucu, orijinal işaretçinin değerine eşittir. Bir nesne bildirildiği takdirde tamamlanmamış olarak kabul edilir, ancak boyutunu veya temel sınıfını belirleyebilmek için yeterli bilgi yok.

**`const`** **`volatile`** Türü bir işaretçiye örtük olarak dönüştürülemeyen veya olmayan herhangi bir nesneye yönelik bir işaretçi `void *` .

### <a name="const-and-volatile-pointers"></a>const ve volatile işaretçiler

C++ **`const`** , veya türünden veya olmayan bir türe standart bir dönüştürme sağlamaz **`volatile`** **`const`** **`volatile`** . Ancak, herhangi bir dönüştürme sıralaması açık tür atamaları (güvenli olmayan dönüştürmeler dahil) kullanılarak belirtilebilir.

> [!NOTE]
> Statik üyelere işaretçiler haricinde üyelere yönelik C++ işaretçileri, normal işaretçilerden farklıdır ve aynı standart Dönüştürmelere sahip değildir. Statik üye işaretçileri normal işaretçilerdir ve normal işaretçilerle aynı dönüştürmeleri vardır.

### <a name="null-pointer-conversions"></a>null işaretçi dönüşümleri

Sıfır olarak değerlendirilen bir integral sabiti ifadesi veya işaretçi türüne bir ifade atama, *null işaretçi* adlı işaretçiye dönüştürülür. Bu işaretçi her zaman, geçerli bir nesne veya işlev işaretçiyle eşit olmayan şekilde karşılaştırılır. Bir özel durum, aynı uzaklığa sahip olabilen ve hala farklı nesnelere işaret eden tabanlı nesneler işaretçileridir.

C++ 11 ' de, [nullptr](../cpp/nullptr.md) türü C stili null İşaretçisinde tercih edilmelidir.

### <a name="pointer-expression-conversions"></a>İşaretçi ifadesi dönüştürmeleri

Dizi türündeki bir ifade, aynı türden bir işaretçiye dönüştürülebilir. Dönüştürme işleminin sonucunda, ilk dizi öğesinin işaretçisi elde edilir. Aşağıdaki örnekte, böyle bir dönüştürme gösterilmektedir:

```cpp
char szPath[_MAX_PATH]; // Array of type char.
char *pszPath = szPath; // Equals &szPath[0].
```

Belirli bir türü döndüren bir işlevle sonuçlanan ifade, aşağıdakiler haricinde bu türü döndüren bir işlevin işaretçisine dönüştürülür:

- İfade, adres işlecinin () bir işleneni olarak kullanılır **&** .

- İfade, işlev çağrısı işlecinin bir işleneni olarak kullanılıyorsa.

## <a name="reference-conversions"></a>Başvuru dönüştürmeleri

Bir sınıfa bir başvuru, bu durumlarda temel sınıfa yönelik başvuruya dönüştürülebilir:

- Belirtilen temel sınıfa erişilebilir.

- Dönüştürme belirsiz değildir. (Belirsiz temel sınıf başvuruları hakkında daha fazla bilgi için bkz. [birden çok temel sınıf](../cpp/multiple-base-classes.md).)

Dönüştürmenin sonucu temel sınıfı temsil eden alt nesne için bir işaretçidir.

## <a name="pointer-to-member"></a>Üye işaretçisi

Sınıf üyeleri için işaretçiler; atama, başlatma, karşılaştırma ve diğer ifadeler sırasında dönüştürülebilir. Bu bölüm aşağıdaki üye işaretçisi dönüştürmelerini açıklar:

### <a name="pointer-to-base-class-member"></a>Taban sınıf üyesine yönelik işaretçi

Aşağıdaki koşullar karşılandığında, temel sınıfın üyesinin işaretçisi sınıfın kendisinden üretilmiş üyesinin işaretçisine dönüştürülebilir:

- Türetilmiş sınıfın işaretçisinden temel sınıf işaretçisine ters dönüştürme erişilebilirdir.

- Türetilmiş sınıf, neredeyse temel sınıftan devralmaz.

Sol işlenen üyenin bir işaretçisi olduğunda, sağ işlenen üye işaretçisi türünde veya 0 olarak değerlendirilen sabit bir ifade olmalıdır. Bu atama, yalnızca aşağıdaki durumlarda geçerlidir:

- Sağ işlenen, sol işlenenle aynı sınıfta olan üyenin bir işaretçisidir.

- Sol işlenen, sağ işlenenin sınıfından genel ve açık olarak türetilmiş sınıfın üyesinin bir işaretçisidir.

### <a name="null-pointer-to-member-conversions"></a>üye dönüştürmeleri için null işaretçi

Sıfır olarak değerlendirilen bir integral sabit ifadesi, null işaretçisine dönüştürülür. Bu işaretçi her zaman, geçerli bir nesne veya işlev işaretçiyle eşit olmayan şekilde karşılaştırılır. Bir özel durum, aynı uzaklığa sahip olabilen ve hala farklı nesnelere işaret eden tabanlı nesneler işaretçileridir.

Aşağıdaki kodda, `i` sınıfındaki `A` üyesinin işaretçisinin tanımı gösterilmektedir. `pai` işaretçisi, null işaretçi olan 0 ile başlatılır.

```cpp
class A
{
public:
int i;
};

int A::*pai = 0;

int main()
{
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ dil başvurusu](../cpp/cpp-language-reference.md)
