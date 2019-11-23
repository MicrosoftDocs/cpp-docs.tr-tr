---
title: Standart dönüşümler
ms.date: 10/02/2019
helpviewer_keywords:
- standard conversions, categories of
- L-values [C++]
- conversions, standard
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
ms.openlocfilehash: c51a5ea5aaabb27babb9e4cd355721742088d31e
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998903"
---
# <a name="standard-conversions"></a>Standart dönüşümler

Dil C++ , temel türleri arasındaki dönüştürmeleri tanımlar. Ayrıca işaretçi, başvuru ve işaretçiden üyeye türetilmiş türler için dönüşümler tanımlar. Bu dönüşümler *Standart dönüşümler*olarak adlandırılır.

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

Bir dönüştürmenin sonucu yalnızca bir başvuru türü üretirse bir l değeridir. Örneğin, `operator int&()` olarak belirtilen kullanıcı tanımlı bir dönüştürme bir başvuru döndürür ve bir l değeri olur. Ancak, `operator int()` olarak belirtilen bir dönüştürme bir nesnesi döndürür ve l değeri değildir.

## <a name="integral-promotions"></a>Integral yükseltmeler

İntegral türündeki nesneler, daha büyük bir değer kümesini temsil eden bir tür olan başka bir geniş integral türüne dönüştürülebilir. Bu dönüştürme türü, *integral yükseltme*olarak adlandırılır. İntegral yükseltme ile, başka bir integral türünün kullanılabileceği her yerde aşağıdaki türleri bir ifadede kullanabilirsiniz:

- **Char** ve **short int** türündeki nesneler, sabit değerler ve sabitler

- Numaralandırma türleri

- **int** bit alanları

- Numaralandırıcılar

C++yükseltmeler, yükseltmeden önceki değer ile aynı olması garantiden sonraki değerin "değer-koruma" değeridir. Değer koruma promosyonları ' nda, daha kısa integral türlerindeki nesneler (örneğin, bit alanları veya **char**türündeki nesneler), **tamsayı** özgün türün tam aralığını temsil ediyorsa **int** türüne yükseltilir. **İnt** tam değer aralığını temsil ediyorsa, nesne **işaretsiz int**türüne yükseltilir.  Bu strateji standart C tarafından kullanılan bir ile aynı olsa da, değer koruma dönüştürmelerinde nesnenin "signedyeti" yoktur.

Değer korumalı yükseltmeler ve işaretli durumu koruyan yükseltmeler normalde aynı sonuçları verir. Ancak, yükseltilen nesne şöyle görünüyorsa farklı sonuçlar üretebilirler:

- `/`, `%`, `/=`, `%=`, `<`, `<=`, `>`veya `>=` işleneni

   Bu işleçler sonucu belirlemek için işareti kullanırlar. Değer koruma ve oturum koruma yükseltmeleri, bu işlenenlere uygulandığında farklı sonuçlar üretir.

- `>>` veya `>>=` sol işleneni

   Bu işleçler, imzalanmış ve işaretsiz miktarları bir vardiya işleminde farklı şekilde işler. İşaretli miktarlar için, bir sağ kaydırma işlemi, işaret biti konumlarına, işaretsiz miktarlar sıfır doldurulurken, işaret bitini bir arada yayar.

- Aşırı yüklenmiş bir işlevin bağımsız değişkeni veya aşırı yüklenmiş bir işlecin işleneni, bağımsız değişken eşleştirme için işlenen türünün signedliğine bağlıdır. Aşırı yüklenmiş işleçleri tanımlama hakkında daha fazla bilgi için bkz. [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md).

## <a name="integral-conversions"></a>Integral dönüştürmeleri

*İntegral dönüştürmeleri* integral türleri arasındaki Dönüştürmelere sahiptir. İntegral türleri **char**, **Short** (veya **short int**), int, **Long**ve **Long Long** **'tir**. Bu türler **imzalı** veya **imzasız**ile nitelenmiş olabilir ve imzasız **int**için toplu **olarak kullanılabilir.**

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

Önceki örnekte, **işaretli bir Short**, `i`tanımlanır ve negatif bir sayı olarak başlatılır. İfade `(u = i)`, `i` `u`atamasından önce işaretsiz bir **Short** 'a dönüştürülmesine neden olur.

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

Yukarıdaki örnekte `u`, ifadeyi `(i = u)`değerlendirmek için işaretli bir miktara dönüştürülmesi gereken **işaretsiz bir kısa** tamsayı nesnesidir. Değeri **işaretli bir kısa**sürede doğru şekilde gösterilemediği için veriler gösterildiği gibi yanlış yorumlanır.

## <a name="floating-point-conversions"></a>Kayan nokta dönüştürmeleri

Kayan türden bir nesne güvenle daha kesin bir kayan türe dönüştürülebilir — diğer bir deyişle, dönüştürme hiçbir anlam kaybına neden olmaz. Örneğin, **float** 'ten **Double** veya **Double** 'tan **Long Double** arasında dönüştürmeler güvenlidir ve değer değiştirilmez.

Kayan türden bir nesne, bu tür tarafından bir Aralık gösterilebilir tablo ise daha az kesin bir türe de dönüştürülebilir. (Kayan türlerin aralıkları için bkz. [kayan sınırlar](../cpp/floating-limits.md) .) Özgün değer tam olarak gösterilemeyen tablo değilse, bir sonraki daha yüksek veya daha düşük gösterilemeyen değere dönüştürülebilir. Bu değer yoksa sonuç tanımsızdır. Aşağıdaki örnek göz önünde bulundurun:

```cpp
cout << (float)1E300 << endl;
```

Türe göre en büyük değer gösterilebilir değeri 3.402823466 E38 — 1E300 ' dan çok daha küçük **bir sayıdır.** Bu nedenle, sayı sonsuz olarak dönüştürülür ve sonuç "INF" dir.

## <a name="conversions-between-integral-and-floating-point-types"></a>İntegral ve kayan nokta türleri arasındaki dönüşümler

Belirli ifadeler, kayan türde nesneleri integral türlerine dönüştürebilirler veya tam tersi olabilir. İntegral türündeki bir nesne kayan bir türe dönüştürüldüğünde ve özgün değer tam olarak gösterilemeyen şekilde görüntülenmiyorsa, sonuç bir sonraki daha yüksek veya daha düşük bir sonraki değer olarak gösterilebilir.

Kayan türden bir nesne integral türüne dönüştürüldüğünde kesirli bölüm *kesilir*veya sıfıra yuvarlanır. 1,3 gibi bir sayı 1 ' e dönüştürülüp-1,3-1 ' e dönüştürülür. Kesilen değer en yüksek gösterilemeyen değerden yüksekse veya en düşük gösterilemeyen değerden düşükse, sonuç tanımsızdır.

## <a name="arithmetic-conversions"></a>Aritmetik dönüştürmeler

Birçok ikili işleç ( [ikili işleçlere sahip ifadelerde](../cpp/expressions-with-binary-operators.md)açıklanmıştır) işlenenlerin dönüştürmelerine neden olur ve aynı şekilde sonuç verir. Bu işleçlerin dönüşümlerine neden olan dönüşümler, *Olağan aritmetik dönüştürmeler*olarak adlandırılır. Farklı yerel türlerine sahip işlenenlerin aritmetik dönüştürmeleri, aşağıdaki tabloda gösterildiği gibi yapılır. Typedef türleri, temel yerel türlerine göre davranır.

### <a name="conditions-for-type-conversion"></a>Tür dönüştürme koşulları

|Koşullar karşılandı|Dönüştürme|
|--------------------|----------------|
|İki işlenen de **Long Double**türünde.|Diğer işlenen **Long Double**türüne dönüştürülür.|
|Önceki koşul karşılanmadı ve iki işlenen de **Double**türündedir.|Diğer işlenen **Double**türüne dönüştürülür.|
|Önceki koşullar karşılanmaz ve her iki işlenen de **float**türündedir.|Diğer işlenen **float**türüne dönüştürülür.|
|Önceki koşullar karşılanmamıştır (işlenenlerden hiçbiri kayan türlerden değil).|İşlenenler integral promosyonları aşağıdaki gibi alır:<br /><br />-İki işlenen de **işaretsiz Long**türünde ise, diğer işlenen **işaretsiz Long**türüne dönüştürülür.<br />-Önceki koşul karşılanmazsa ve her iki işlenen de **Long** türünde ve diğeri **işaretsiz int**türünde ise, her iki işlenen de **imzasız Long**türüne dönüştürülür.<br />-Önceki iki koşul karşılanmazsa ve iki işlenen de **Long**türünde ise, diğer işlenen de **Long**türüne dönüştürülür.<br />-Önceki üç koşul karşılanmazsa ve iki işlenen de **işaretsiz int**türünde ise, diğer işlenen **işaretsiz int**türüne dönüştürülür.<br />-Önceki koşullardan hiçbiri karşılanmazsa her iki işlenen de **int**türüne dönüştürülür.|

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

Yukarıdaki örnekte bulunan ilk deyim, iki integral türü olan `iVal` ve `ulVal`'ın çarpımını göstermektedir. Koşul, hiçbir işlenenin kayan türde olmadığı ve bir işlenenin **işaretsiz int**türünde olduğu durumdur. Bu nedenle, `iVal`diğer işleneni **işaretsiz int**türüne dönüştürülür. Sonuç daha sonra `dVal`atanır. Burada yer alan koşul, bir işlenenin **Double**türünde olması, bu nedenle çarpın **işaretsiz tamsayı** sonucu **Double**türüne dönüştürülür.

Yukarıdaki örnekteki ikinci ifadede bir **float** ve integral türünün eklenmesi gösterilmektedir: `fVal` ve `ulVal`. `ulVal` değişkeni **float** türüne dönüştürülür (tablodaki üçüncü koşul). Eklemenin sonucu, **Double** türüne dönüştürülür (tablodaki ikinci koşul) ve `dVal`atanır.

## <a name="pointer-conversions"></a>İşaretçi Dönüştürmeler

İşaretçiler atama, başlatma, karşılaştırma ve diğer ifadeler sırasında dönüştürülebilir.

### <a name="pointer-to-classes"></a>Sınıfların işaretçisi

Bir sınıfa yönelik işaretçinin, temel sınıfa olan işaretçiye dönüştürülebileceği iki durum vardır.

İlk durum, belirtilen temel sınıfa erişilebilir olduğu ve dönüştürmenin belirsiz olduğu durumdur. Belirsiz temel sınıf başvuruları hakkında daha fazla bilgi için bkz. [birden çok temel sınıf](../cpp/multiple-base-classes.md).

Temel bir sınıfa erişilebilir olup olmadığı, türetmede kullanılan devralmanın türüne bağlıdır. Aşağıdaki şekilde gösterilen devralmayı göz önünde bulundurun.

![Temel sınıf erişilebilirliğini gösteren&#45;](../cpp/media/vc38xa1.gif "&#45;") temel sınıf erişilebilirlik devralma grafiğini gösteren devralma grafiği <br/>
Temel sınıf erişilebilirliği çizimi için devralma grafiği

Aşağıdaki tabloda, şekilde gösterildiği durumlar için temel sınıf erişilebilirliği gösterilmektedir.

|Işlevin türü|Mede|Dönüştürme<br /><br /> B * bir\* yasal mı?|
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

Bu tür bir dönüştürmenin sonucu, nesnenin temel sınıf tarafından tamamen tanımlanan bölümü olan *alt nesne için*bir işaretçidir.

Aşağıdaki kod, `B` `A`türetildiği `A` ve `B`iki sınıfı tanımlar. (Devralma hakkında daha fazla bilgi için bkz. [türetilmiş sınıflar](../cpp/inheritance-cpp.md).) Daha sonra `bObject`, `B`türünde bir nesne ve nesneyi işaret eden iki işaretçi (`pA` ve `pB`) tanımlar.

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

İşaretçi `pA`, anlamı "`A`türünde bir nesne işaretçisi olarak yorumlanabilen `A *`türüdür. `bObject` üyeleri (`BComponent` ve `BMemberFunc`gibi), `B` yazmak için benzersizdir ve bu nedenle `pA`üzerinden erişilmez. `pA` işaretçisi, yalnızca sınıf `A`tanımlanmış nesnenin özelliklerine (üye işlevleri ve veriler) erişim sağlar.

### <a name="pointer-to-function"></a>İşlev işaretçisi

Tür `void *`, bu işaretçiyi tutacak kadar büyükse, bir işlev işaretçisi `void *`türüne dönüştürülebilir.

### <a name="pointer-to-void"></a>Void işaretçisi

**Void** türü işaretçiler, diğer herhangi bir türe işaretçilere dönüştürülebilir, ancak yalnızca açık tür saçılması (C 'nin aksine). Herhangi bir türe yönelik bir işaretçi örtük olarak **void**türünde bir işaretçiye dönüştürülebilir. Bir türün tamamlanmamış bir nesnesine yönelik bir işaretçi, **void** (örtük) ve geri (açıkça) işaretçisine dönüştürülebilir. Bu tür bir dönüştürmenin sonucu, orijinal işaretçinin değerine eşittir. Bir nesne bildirildiği takdirde tamamlanmamış olarak kabul edilir, ancak boyutunu veya temel sınıfını belirleyebilmek için yeterli bilgi yok.

**Const** veya **volatile** olmayan herhangi bir nesneye yönelik bir işaretçi, örtük olarak `void *`türünde bir işaretçiye dönüştürülebilir.

### <a name="const-and-volatile-pointers"></a>const ve volatile işaretçiler

C++**const veya** **volatile** türünden **const** veya **volatile**olmayan bir türe Standart dönüştürme sağlamaz. Ancak, herhangi bir dönüştürme sıralaması açık tür atamaları (güvenli olmayan dönüştürmeler dahil) kullanılarak belirtilebilir.

> [!NOTE]
> C++statik üyelere işaretçiler haricinde üye işaretçileri, normal işaretçilerden farklıdır ve aynı standart Dönüştürmelere sahip değildir. Statik üye işaretçileri normal işaretçilerdir ve normal işaretçilerle aynı dönüştürmeleri vardır.

### <a name="null-pointer-conversions"></a>null işaretçi dönüşümleri

Sıfır olarak değerlendirilen bir integral sabiti ifadesi veya işaretçi türüne bir ifade atama, *null işaretçi*adlı işaretçiye dönüştürülür. Bu işaretçi her zaman, geçerli bir nesne veya işlev işaretçiyle eşit olmayan şekilde karşılaştırılır. Bir özel durum, aynı uzaklığa sahip olabilen ve hala farklı nesnelere işaret eden tabanlı nesneler işaretçileridir.

C++ 11 ' de, [nullptr](../cpp/nullptr.md) türü C stili null İşaretçisinde tercih edilmelidir.

### <a name="pointer-expression-conversions"></a>İşaretçi ifadesi dönüştürmeleri

Dizi türündeki bir ifade, aynı türden bir işaretçiye dönüştürülebilir. Dönüştürme işleminin sonucunda, ilk dizi öğesinin işaretçisi elde edilir. Aşağıdaki örnekte, böyle bir dönüştürme gösterilmektedir:

```cpp
char szPath[_MAX_PATH]; // Array of type char.
char *pszPath = szPath; // Equals &szPath[0].
```

Belirli bir türü döndüren bir işlevle sonuçlanan ifade, aşağıdakiler haricinde bu türü döndüren bir işlevin işaretçisine dönüştürülür:

- İfade, adres işlecinin ( **&** ) işleneni olarak kullanılır.

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

[C++dil başvurusu](../cpp/cpp-language-reference.md)