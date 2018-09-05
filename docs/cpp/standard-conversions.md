---
title: Standart dönüştürmeler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- standard conversions, categories of
- L-values [C++]
- conversions, standard
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2e8a69cf7f118af8753ebcb9e0e150c8dfc0859
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43687319"
---
# <a name="standard-conversions"></a>Standart Dönüşümler
C++ dili, temel türler arasında dönüştürmeler tanımlar. Ayrıca, işaretçi, başvuru için dönüştürmeleri tanımlar ve üye işaretçisi türetilmiş türler. Bu dönüştürmeler adlı *standart dönüştürmeler*.  
  
 Bu bölümde, aşağıdaki standart dönüştürmeler ele alınmaktadır:  
  
-   Tamsayı yükseltmeleri  
  
-   Tamsayı dönüştürmeleri  
  
-   Kayan dönüştürmeler  
  
-   Kayan ve tam sayı dönüşümleri  
  
-   Aritmetik dönüştürmeler  
  
-   İşaretçi dönüşümleri  
  
-   Başvuru dönüşümleri  
  
-   İşaretçi-üye dönüşümleri  
  
    > [!NOTE]
    >  Kullanıcı tanımlı türler, kendi dönüştürmeleri belirtebilirsiniz. Kullanıcı tanımlı tür dönüştürme alınmıştır [oluşturucular](../cpp/constructors-cpp.md) ve [dönüştürmeler](../cpp/user-defined-type-conversions-cpp.md).  
  
Aşağıdaki kod, dönüştürmeler (Bu örnekte, integral yükseltmeler) neden olur:  
  
```cpp 
long  long_num1, long_num2;  
int   int_num;  
  
// int_num promoted to type long prior to assignment.  
long_num1 = int_num;  
  
// int_num promoted to type long prior to multiplication.  
long_num2 = int_num * long_num2;  
```  
  
 Yalnızca bir başvuru türü oluşturursa bir dönüştürmenin sonucunu bir l değeridir. Örneğin, bir kullanıcı tanımlı dönüştürme olarak bildirilen `operator int&()` bir başvuru döndürür ve bir l değeridir. Ancak, bir dönüştürme olarak bildirilen `operator int()`bir nesne döndürür ve bir l değeri değildir.  
  
## <a name="integral-promotions"></a>Tamsayı yükseltmeleri  
 İntegral türünde nesneler daha geniş başka bir integral türüne (yani daha büyük değerler kümesini temsil edebilen bir tür) dönüştürülebilir. Genişleten türden böyle bir dönüştürmeye "integral yükseltme" denir. İntegral yükseltme ile, başka bir integral türünün kullanılabildiği yerlerde, aşağıdakileri bir ifade içinde kullanabilirsiniz:  
  
-   Nesneler, değişmez değerler ve tür sabitleri **char** ve **kısa tamsayı**  
  
-   Numaralandırma türleri  
  
-   **int** bit alanları  
  
-   Numaralandırıcılar  
  
 C++ yükseltmeleri "değer korumalıdır." Diğer bir deyişle, yükseltmeden sonraki değerin yükseltmeden önceki değeri ile aynı olması sağlanır. Değer korumalı yükseltmelerde, daha kısa integral türündeki nesneler (bit alanları veya türündeki nesneler gibi **char**) türüne yükseltilir **int** varsa **int** tam temsil edebilir özgün türün aralığı. Varsa **int** nesne türüne yükseltilir değerlerini tam aralığını temsil edemez **işaretsiz int**. Bu strateji ANSI C tarafından kullanılan stratejiyle aynı olsa da, değer korumalı dönüştürme işlemlerinde nesnenin "işaretli durumu" korunmaz.  
  
 Değer korumalı yükseltmeler ve işaretli durumu koruyan yükseltmeler normalde aynı sonuçları verir. Ancak, yükseltilen nesne aşağıdakilerden biri ise farklı sonuçlar üretebilirler:  
  
-   Bir işleneni **/**, `%`, `/=`, `%=`, **<**, **\< =**, **>**, veya **>=**  
  
     Bu işleçler sonucu belirlemek için işareti kullanırlar. Bu nedenle, değer korumalı ve işaret korumalı yükseltmeler bu işleçlere uygulandığında farklı sonuçlar verir.  
  
-   Sol işleneni **>>** veya **>>=**  
  
     Bu işleçler, kaydırma işlemi yapılırken işaretli ve işaretsiz miktarları farklı şekilde ele alırlar. İşaretli miktarlar için, bir miktarı sağa kaydırmak işaret bitinin boşaltılmış bit konumlarına dağıtılmasına neden olur. İşaretsiz miktarlar için, boşaltılmış bit konumları sıfırla dolguludur.  
  
-   Aşırı yüklenmiş bir işleve yönelik bir bağımsız değişken veya bağımsız değişken eşleştirme için ilgili işlecin türünün işaretli durumuna bağlı olan aşırı yüklenmiş bir işlecin işleci. (Bkz [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md) tanımlama hakkında daha fazla bilgi için aşırı yüklenmiş işleçler.)  
  
## <a name="integral-conversions"></a>Tamsayı dönüştürmeleri  
 İntegral dönüştürmeler integral türleri arasında gerçekleştirilir. İntegral türleri **char**, **int**, ve **uzun** (ve **kısa**, **imzalı**ve **işaretsiz** sürümleri bu tür).  
  
 **İmzasıza dönüştürme**  
  
 İşaretli integral türlerindeki nesneler, ilgili işaretsiz türlere dönüştürülebilir. Bu dönüştürme işlemleri gerçekleştirildiğinde, gerçek bit deseni değişmez; ancak, verilerin yorumlanması değişir. Bu kodu göz önünde bulundurun:  
  
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
  
 Yukarıdaki örnekte, bir **kısa imzalı**, `i`tanımlanır ve negatif bir sayıda başlatılır. İfade `(u = i)` neden `i` dönüştürülecek bir **işaretsiz** atama için önce `u`.  
  
 **İmzalı işaretsiz**  
  
 İşaretsiz integral türlerindeki nesneler, ilgili işaretli türlere dönüştürülebilir. Ancak böyle bir dönüştürme, işaretsiz nesnenin değeri işaretli tür tarafından gösterilebilen aralığın dışındaysa aşağıdaki örnekte gösterildiği gibi verilerin yanlış yorumlanmasına neden olabilir:  
  
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
  
 Önceki örnekte `u` olduğu bir **işaretsiz** ifadeyi değerlendirmek için işaretli bir miktara dönüştürülmesi gereken integral nesnesidir `(i = u)`. Değeri doğru olarak gösterilemez çünkü bir **kısa imzalı**, gösterildiği gibi verilerin yanlış.  
  
## <a name="floating-point-conversions"></a>Kayan noktadan dönüştürme  
 Kayan türden bir nesne güvenle daha kesin bir kayan türe dönüştürülebilir — diğer bir deyişle, dönüştürme hiçbir anlam kaybına neden olmaz. Örneğin, Dönüştürmelere **float** için **çift** veya **çift** için **uzun çift** güvenli olduğunu ve değer değişmez.  
  
 Kayan türden bir nesne daha az kesin bir türe de dönüştürülebilir (o tür tarafından gösterilebilen bir aralıkta ise). (Bkz [kayan sınırları](../cpp/floating-limits.md) kayan tür aralıkları için.) Özgün değer tam olarak gösterilebiliyorsa, bir sonraki daha yüksek veya daha düşük gösterilebilir değere dönüştürülebilir. Böyle bir değer yoksa, sonuç tanımsızdır. Aşağıdaki örnek göz önünde bulundurun:  
  
```cpp
cout << (float)1E300 << endl;  
```  
  
 En büyük değer türü **float** 3.402823466E38 değeridir; 1E300'den bir çok daha az sayıda. Bu nedenle, sayı sonsuza dönüştürülür ve sonuç "INF" olur.  
  
## <a name="conversions-between-integral-and-floating-point-types"></a>İntegral ve kayan nokta türleri arasında dönüştürmeler  
 Belirli ifadeler, kayan türde nesneleri integral türlerine dönüştürebilirler veya tam tersi olabilir. İntegral türündeki bir nesne kayan bir türe dönüştürüldüğünde ve orijinal değeri tam olarak temsil edilemediğinde, sonuç ya bir sonraki daha yüksek ya da daha düşük temsil edilebilir değerdir.  
  
 Kayan türde bir nesne bir integral türe dönüştürüldüğünde, kesirli kısmı kesilir. Yuvarlama, dönüştürme işleminde yer almaz. Kesme, 1,3 1 ve-1.3 dönüştürülür gibi bir sayının -1 olarak dönüştürülür anlamına gelir.  
  
## <a name="arithmetic-conversions"></a>Aritmetik dönüştürmeler  
 Çoğu ikili işleç (ele [ikili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)), işlenenlerin dönüştürülmesine neden olur ve sonuçları aynı şekilde. Bu işleçlerin dönüştürmelere neden olduğu işleme "normal aritmetik dönüştürme" adı verilir. Farklı yerel türlerden işlenenlerin aritmetik dönüştürmeleri, aşağıdaki tabloda gösterildiği gibi gerçekleştirilir. Typedef türleri, temel yerel türlerine göre davranır.  
  
### <a name="conditions-for-type-conversion"></a>Tür Dönüştürme için Koşullar  
  
|Sağlanan Koşullar|Dönüştürme|  
|--------------------|----------------|  
|İki işlenenden türünde **uzun çift**.|Diğer işlenen türüne dönüştürülür **uzun çift**.|  
|Önceki koşul karşılanmamıştır ve işlenenlerden türüdür **çift**.|Diğer işlenen türüne dönüştürülür **çift**.|  
|Önceki koşullar karşılanmamıştır ve işlenenlerden türüdür **float**.|Diğer işlenen türüne dönüştürülür **float**.|  
|Önceki koşullar karşılanmamıştır (işlenenlerden hiçbiri kayan türlerden değil).|İntegral yükseltmeler işlenenler üzerinde aşağıdaki gibi gerçekleştirilir:<br /><br /> -Eğer iki işlenenden türünde **işaretsiz uzun**, diğer işlenen türüne dönüştürülür **işaretsiz uzun**.<br />-Koşul karşılanmamışsa ve işlenenlerden türü ise **uzun** ve diğer tür **işaretsiz int**, her iki işlenen de türüne dönüştürülür **işaretsiz uzun**.<br />-Önceki iki koşul karşılanmazsa ve işlenenlerden türü ise **uzun**, diğer işlenen türüne dönüştürülür **uzun**.<br />-Önceki üç koşul karşılanmazsa ve işlenenlerden türü ise **işaretsiz int**, diğer işlenen türüne dönüştürülür **işaretsiz int**.<br />-Önceki koşullardan hiçbiri karşılanırsa, her iki işlenen de türüne dönüştürülür **int**.|  
  
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
  
 Yukarıdaki örnekte bulunan ilk deyim, iki integral türü olan `iVal` ve `ulVal`'ın çarpımını göstermektedir. Sağlanan koşul, iki işlenenin de kayan türden olmaması ve bir işlenenin türüdür olan **işaretsiz int**. Bu nedenle diğer işlenen `iVal`, türüne dönüştürülür **işaretsiz int**. Sonuç `dVal`'a atanır. Sağlanan koşul, bir işlenenin türünden olmasıdır **çift**; bu nedenle **işaretsiz int** çarpma işleminin sonucu türüne dönüştürülür **çift**.  
  
 Önceki örnekte bulunan ikinci deyim eklenmesini gösteren bir **float** ve integral türü `fVal` ve `ulVal`. `ulVal` Değişkenin türüne dönüştürülür **float** (üçüncü tabloda koşul). Ek sonuç türüne dönüştürülür **çift** (ikinci tabloda koşul) ve atanan `dVal`.  
  
## <a name="pointer-conversions"></a>İşaretçi dönüşümleri  
 İşaretçiler atama, başlatma, karşılaştırma ve diğer ifadeler sırasında dönüştürülebilir.  
  
### <a name="pointer-to-classes"></a>Sınıflar işaretçisi  
 Bir işaretçiyi bir sınıf içinde temel sınıf işaretçisine dönüştürülebilir iki durum vardır.  
  
 İlk durum belirtilen temel sınıf erişilebilirdir ve dönüştürme belirsiz olduğunda geçerlidir. (Bkz [birden çok taban sınıfı](../cpp/multiple-base-classes.md) belirsiz temel sınıf başvuruları hakkında daha fazla bilgi.)  
  
 Bir temel sınıf erişilebilir olup türetme içinde kullanılan devralma türüne bağlıdır. Aşağıdaki şekilde gösterilen devralma göz önünde bulundurun.  
  
 ![Temel gösteren Devralma Grafiği&#45;sınıf erişilebilirlik](../cpp/media/vc38xa1.gif "vc38XA1")  
Temel sınıf erişilebilirlik gösterimi için devralma grafiği  
  
 Aşağıdaki tabloda görüldüğü durumda için temel sınıf erişilebilirlik gösterilmektedir.  
  
### <a name="base-class-accessibility"></a>Temel sınıf erişilebilirlik  
  
|İşlev türü|Türetme|Dönüştürme<br /><br /> B * a\* yasal?|  
|----------------------|----------------|-------------------------------------------|  
|Dış (olmayan sınıf kapsamlı) işlevi|Özel|Hayır|  
||Korumalı|Hayır|  
||Ortak|Evet|  
|(B kapsamda) B üye işlevi|Özel|Evet|  
||Korumalı|Evet|  
||Ortak|Evet|  
|C üye işlevi (C kapsamda)|Özel|Hayır|  
||Korumalı|Evet|  
||Ortak|Evet|  
  
 Açık tür dönüştürme kullandığınızda bir işaretçiyi bir sınıf içinde temel sınıf işaretçisine dönüştürülebilir ikinci durumdur. (Bkz [açık tür dönüştürme işleci](explicit-type-conversion-operator-parens.md) açık tür dönüştürmeleri hakkında daha fazla bilgi.)  
  
 Böyle bir dönüştürmenin sonucu bir "alt nesnesine," bölümünü tamamen taban sınıfı tarafından tanımlanan nesne işaretçisidir.  
  
 Aşağıdaki kod, iki sınıf tanımlar `A` ve `B`burada `B` türetilir `A`. (Devralma hakkında daha fazla bilgi için bkz. [türetilmiş sınıflar](../cpp/inheritance-cpp.md).) Ardından tanımlar `bObject`, türünde bir nesne `B`ve iki işaretçiler (`pA` ve `pB`) nesneye işaret.  
  
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
  
 İşaretçi `pA` türünde `A *`, yorumlanabilen olarak anlamı "türünde bir nesne işaretçisi `A`." Üyeleri `bObject` `(`gibi `BComponent` ve `BMemberFunc`) türüne özgü `B` ve bu nedenle üzerinden erişilemeyen `pA`. `pA` İşaretçi sınıfta tanımlanan yalnızca bu özellikleri (üye işlevleri ve veriler) nesne erişim sağlar `A`.  
  
### <a name="pointer-to-function"></a>İşlev işaretçisi  
 Bir işlev işaretçisi türüne dönüştürülebilir `void *`, türü `void *` işaretçiyle tutabilecek kadar büyük olduğundan.  
  
### <a name="pointer-to-void"></a>Ukazatel na void  
 Türü işaretçiler **void** işaretçileri herhangi bir tür, ancak yalnızca bir açık tür dönüştürme ile dönüştürülebilir (aksine c). Herhangi bir tür için bir işaretçi işaretçisi türüne örtük olarak dönüştürülebilir **void**. Bir işaretçi türü eksik bir nesneye bir işaretçiye dönüştürülebilir **void** (örtük) ve (açıkça). Böyle bir dönüştürmenin sonucu özgün işaretçi değerine eşittir. Bir nesne bildirildiği, ancak kendi boyutunu veya temel sınıf belirlemek kullanılabilir yeterli bilgi eksik olarak kabul edilir.  
  
 Değil herhangi bir nesneye bir işaretçi **const** veya **geçici** türünde bir işaretçi örtük olarak dönüştürülebilir `void *`.  
  
### <a name="const-and-volatile-pointers"></a>const ve volatile işaretçileri  
 C++ standart bir dönüşüm sağlamazsa bir **const** veya **geçici** türü olmayan bir türe **const** veya **geçici**. Ancak, herhangi bir tür dönüştürme açık tür atamaları (güvenli olmayan dönüştürmeler de dahil olmak üzere) kullanılarak belirtilebilir.  
  
> [!NOTE]
>  C++ statik üye işaretçileri dışındaki bir üye işaretçileri normal işaretçilerinden farklı ve aynı standart dönüştürmeler izniniz yok. Statik üye işaretçileri normal işaretçiler ve normal işaretçileri olarak aynı dönüştürmeleri vardır.   
  
### <a name="null-pointer-conversions"></a>null işaretçi dönüşümleri  
 Sıfır olarak değerlendirilen bir integral sabit ifadesi veya işaretçi türüne dönüştürme böyle bir ifade "null işaretçi." adlı bir işaretçiye dönüştürülür Bu işaretçinin, herhangi bir geçerli nesne veya işlevin işaretçisiyle eşit olmayacak şekilde değerlendirileceği garanti edilir (aynı uzaklığa sahip olan, ancak farklı nesnelere işaret edebilen işaretçi tabanlı nesneler dışında).  
  
 C ++ 11'de [nullptr](../cpp/nullptr.md) türü C stili null işaretçisine tercih edilen olmalıdır.  
  
### <a name="pointer-expression-conversions"></a>İşaretçi ifadesi dönüşümleri  
 Dizi türündeki bir ifade, aynı türden bir işaretçiye dönüştürülebilir. Dönüştürme işleminin sonucunda, ilk dizi öğesinin işaretçisi elde edilir. Aşağıdaki örnekte, böyle bir dönüştürme gösterilmektedir:  
  
```cpp 
char szPath[_MAX_PATH]; // Array of type char.  
char *pszPath = szPath; // Equals &szPath[0].  
```  
  
 Belirli bir türü döndüren bir işlevle sonuçlanan ifade, aşağıdakiler haricinde bu türü döndüren bir işlevin işaretçisine dönüştürülür:  
  
-   İfade, adres işlecinin işleneni olarak kullanılıyorsa (**&**).  
  
-   İfade, işlev çağrısı işlecinin bir işleneni olarak kullanılıyorsa.  
  
## <a name="reference-conversions"></a>Başvuru dönüşümleri  
 Bir sınıf için bir başvuru aşağıdaki durumlarda bir temel sınıf için bir başvuruya dönüştürülebilir:  
  
-   Belirtilen temel sınıf erişilebilir.  
  
-   Dönüştürme belirsiz değildir. (Bkz [birden çok taban sınıfı](../cpp/multiple-base-classes.md) belirsiz temel sınıf başvuruları hakkında daha fazla bilgi.)  
  
 Dönüştürmenin sonucu temel sınıfı temsil eden alt nesne için bir işaretçidir.  
  
## <a name="pointer-to-member"></a>Üye işaretçisi  
 Sınıf üyeleri için işaretçiler; atama, başlatma, karşılaştırma ve diğer ifadeler sırasında dönüştürülebilir. Bu bölüm aşağıdaki üye işaretçisi dönüştürmelerini açıklar:  
  
## <a name="pointer-to-base-class-member"></a>Temel sınıf üye işaretçisi  
 Aşağıdaki koşullar karşılandığında, temel sınıfın üyesinin işaretçisi sınıfın kendisinden üretilmiş üyesinin işaretçisine dönüştürülebilir:  
  
-   Türetilmiş sınıfın işaretçisinden temel sınıf işaretçisine ters dönüştürme erişilebilirdir.  
  
-   Türetilmiş sınıf, neredeyse temel sınıftan devralmaz.  
  
 Sol işlenen üyenin bir işaretçisi olduğunda, sağ işlenen üye işaretçisi türünde veya 0 olarak değerlendirilen sabit bir ifade olmalıdır. Bu atama, yalnızca aşağıdaki durumlarda geçerlidir:  
  
-   Sağ işlenen, sol işlenenle aynı sınıfta olan üyenin bir işaretçisidir.  
  
-   Sol işlenen, sağ işlenenin sınıfından genel ve açık olarak türetilmiş sınıfın üyesinin bir işaretçisidir.  
  
## <a name="integral-constant-conversions"></a>Tamsayı sabit dönüştürmeleri  
 Sıfır olarak değerlendirilen bir integral sabiti ifadesi, "null işaretçi" adı verilen bir işaretçiye dönüştürülür. Bu işaretçinin, herhangi bir geçerli nesne veya işlevin işaretçisiyle eşit olmayacak şekilde değerlendirileceği garanti edilir (aynı uzaklığa sahip olan, ancak farklı nesnelere işaret edebilen işaretçi tabanlı nesneler dışında).  
  
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
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)