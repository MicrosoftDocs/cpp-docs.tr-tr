---
title: Standart dönüşümler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- standard conversions, categories of
- L-values [C++]
- conversions, standard
ms.assetid: ce7ac8d3-5c99-4674-8229-0672de05528d
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bdb7477d0ea07803bf2219118e1fb530a889118c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="standard-conversions"></a>Standart Dönüşümler
C++ dili temel türleri arasında dönüştürmeler tanımlar. İşaretçi, başvuru, dönüştürmelerde de tanımlar ve işaretçi-üye türetilmiş tür. Bu dönüşümleri "standart dönüşümler." olarak adlandırılır (Türleri, standart türler ve türetilmiş türler hakkında daha fazla bilgi için bkz: [türleri](http://msdn.microsoft.com/en-us/6882ee83-ea32-4373-8d57-c3efbbc15af0).)  
  
 Bu bölümde aşağıdaki standart dönüşümler ele alınmıştır:  
  
-   Tamsayı yükseltmeleri  
  
-   Tamsayı dönüşümleri  
  
-   Kayan dönüştürmeler  
  
-   Kayan ve tam sayı dönüşümleri  
  
-   Aritmetik dönüşümler  
  
-   İşaretçi dönüşümleri  
  
-   Başvuru dönüşümleri  
  
-   İşaretçi-üye dönüşümleri  
  
    > [!NOTE]
    >  Kullanıcı tanımlı türler kendi dönüşümleri belirtebilirsiniz. Kullanıcı tanımlı türler dönüştürülmesi kapsanan [oluşturucular](../cpp/constructors-cpp.md) ve [dönüşümleri](../cpp/user-defined-type-conversions-cpp.md).  
  
 Aşağıdaki kod Dönüşümleri (Bu örnekte, tamsayı yükseltmeleri) neden olur:  
  
```  
long  long_num1, long_num2;  
int   int_num;  
  
// int_num promoted to type long prior to assignment.  
long_num1 = int_num;  
  
// int_num promoted to type long prior to multiplication.  
long_num2 = int_num * long_num2;  
```  
  
 Bir dönüştürme sonucu l-değeri ise yalnızca bir başvuru türü üretir. Örneğin, kullanıcı tanımlı bir dönüştürme olarak bildirilen `operator int&()` l-değeri ve bir başvuru döndürür. Ancak, bir dönüştürme olarak bildirilen `operator int()`bir nesne döndürür ve bir l-değeri değil.  
  
## <a name="integral-promotions"></a>Tamsayı yükseltmeleri  
 İntegral türünde nesneler daha geniş başka bir integral türüne (yani daha büyük değerler kümesini temsil edebilen bir tür) dönüştürülebilir. Genişleten türden böyle bir dönüştürmeye "integral yükseltme" denir. İntegral yükseltme ile, başka bir integral türünün kullanılabildiği yerlerde, aşağıdakileri bir ifade içinde kullanabilirsiniz:  
  
-   Nesneler, değişmez değerler ve `char` ile `short int` türünde sabitler.  
  
-   Numaralandırma türleri  
  
-   `int` bit alanları  
  
-   Numaralandırmalar  
  
 C++ yükseltmeleri "değer korumalıdır." Diğer bir deyişle, yükseltmeden sonraki değerin yükseltmeden önceki değeri ile aynı olması sağlanır. Değer korumalı yükseltmelerde, daha kısa integral türündeki nesneler (bit alanları veya `char` türündeki nesneler gibi) `int` türüne yükseltilir (`int` özgün türün tamamını temsil edebiliyorsa). `int` değerlerin tam aralığını temsil edemiyorsa, nesne `unsigned int` türüne yükseltilir. Bu strateji ANSI C tarafından kullanılan stratejiyle aynı olsa da, değer korumalı dönüştürme işlemlerinde nesnenin "işaretli durumu" korunmaz.  
  
 Değer korumalı yükseltmeler ve işaretli durumu koruyan yükseltmeler normalde aynı sonuçları verir. Ancak, yükseltilen nesne aşağıdakilerden biri ise farklı sonuçlar üretebilirler:  
  
-   Bir işleneni **/**, `%`, `/=`, `%=`, **<**, **\< =**, **>**, veya **>=**  
  
     Bu işleçler sonucu belirlemek için işareti kullanırlar. Bu nedenle, değer korumalı ve işaret korumalı yükseltmeler bu işleçlere uygulandığında farklı sonuçlar verir.  
  
-   Sol işleneni **>>** veya **>>=**  
  
     Bu işleçler, kaydırma işlemi yapılırken işaretli ve işaretsiz miktarları farklı şekilde ele alırlar. İşaretli miktarlar için, bir miktarı sağa kaydırmak işaret bitinin boşaltılmış bit konumlarına dağıtılmasına neden olur. İşaretsiz miktarlar için, boşaltılmış bit konumları sıfırla dolguludur.  
  
-   Aşırı yüklenmiş bir işleve yönelik bir bağımsız değişken veya bağımsız değişken eşleştirme için ilgili işlecin türünün işaretli durumuna bağlı olan aşırı yüklenmiş bir işlecin işleci. (Bkz [aşırı yüklenmiş işleçler](../cpp/operator-overloading.md) tanımlama hakkında daha fazla bilgi için aşırı yüklenmiş işleçler.)  
  
## <a name="integral-conversions"></a>Tamsayı dönüşümleri  
 İntegral dönüştürmeler integral türleri arasında gerçekleştirilir. Tam sayı türleri `char`, `int`, ve **uzun** (ve **kısa**, **imzalı**, ve `unsigned` sürümleri bu tür).  
  
 **İmzasız için imzalanmış**  
  
 İşaretli integral türlerindeki nesneler, ilgili işaretsiz türlere dönüştürülebilir. Bu dönüştürme işlemleri gerçekleştirildiğinde, gerçek bit deseni değişmez; ancak, verilerin yorumlanması değişir. Bu kodu göz önünde bulundurun:  
  
```  
  
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
  
 Yukarıdaki örnekte, bir `signed short`, `i` tanımlanır ve negatif bir sayıda başlatılır. İfade `(u = i)` neden `i` dönüştürülecek bir **kısa imzasız** atamayı önce `u`.  
  
 **İmzalı imzalanmamış**  
  
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
  
 Önceki örnekte `u` olan bir `unsigned` **kısa** ifade değerlendirmek için imzalanmış bir miktar dönüştürülmelidir tam sayı nesne `(i = u)`. Değeri `signed short` içinde düzgün bir şekilde gösterilemediği için veriler gösterildiği gibi yanlış yorumlanır.  
  
## <a name="floating-point-conversions"></a>Kayan noktayı dönüştürme  
 Kayan türden bir nesne güvenle daha kesin bir kayan türe dönüştürülebilir — diğer bir deyişle, dönüştürme hiçbir anlam kaybına neden olmaz. Örneğin, gelen dönüşümleri **float** için **çift** veya **çift** için `long double` güvenli olduğunu ve değer değişmez.  
  
 Kayan türden bir nesne daha az kesin bir türe de dönüştürülebilir (o tür tarafından gösterilebilen bir aralıkta ise). (Bkz [kayan sınırları](../cpp/floating-limits.md) türleri kayan aralıkları için.) Özgün değer tam olarak gösterilebiliyorsa, bir sonraki daha yüksek veya daha düşük gösterilebilir değere dönüştürülebilir. Böyle bir değer yoksa, sonuç tanımsızdır. Aşağıdaki örnek göz önünde bulundurun:  
  
```cpp
cout << (float)1E300 << endl;  
```  
  
 Türe göre gösterilebilir maksimum değer **float** 3.402823466E38 olan — çok daha küçük bir sayı 1E300 daha. Bu nedenle, sayı sonsuza kadar dönüştürülür ve "INF" sonucudur.  
  
## <a name="conversions-between-integral-and-floating-point-types"></a>Tam sayı ve kayan nokta türleri arasında dönüştürmeler  
 Belirli ifadeler, kayan türde nesneleri integral türlerine dönüştürebilirler veya tam tersi olabilir. İntegral türündeki bir nesne kayan bir türe dönüştürüldüğünde ve orijinal değeri tam olarak temsil edilemediğinde, sonuç ya bir sonraki daha yüksek ya da daha düşük temsil edilebilir değerdir.  
  
 Kayan türde bir nesne bir integral türe dönüştürüldüğünde, kesirli kısmı kesilir. Yuvarlama, dönüştürme işleminde yer almaz. Kesme 1.3 1 ve-1.3 dönüştürülür gibi bir sayı -1 olarak dönüştürülür anlamına gelir.  
  
## <a name="arithmetic-conversions"></a>Aritmetik dönüşümler  
 Birçok ikili işleçler (ele [ikili işleçli ifadeler](../cpp/expressions-with-binary-operators.md)) işlenenleri dönüştürülme neden ve sonuçları aynı şekilde verim. Bu işleçlerin dönüştürmelere neden olduğu işleme "normal aritmetik dönüştürme" adı verilir. Farklı yerel türlerden işlenenlerin aritmetik dönüştürmeleri, aşağıdaki tabloda gösterildiği gibi gerçekleştirilir. Typedef türleri, temel yerel türlerine göre davranır.  
  
### <a name="conditions-for-type-conversion"></a>Tür Dönüştürme için Koşullar  
  
|Sağlanan Koşullar|Dönüştürme|  
|--------------------|----------------|  
|Her iki işlenen türünde **uzun çift**.|Diğer işlenen türü için dönüştürülür **uzun çift**.|  
|Koşulu karşılanmadı ve her iki işlenen önceki türüdür **çift**.|Diğer işlenen türü için dönüştürülür **çift**.|  
|Koşulları karşılanmadı ve her iki işlenen önceki türüdür **float**.|Diğer işlenen türü için dönüştürülür **float**.|  
|Önceki koşullar karşılanmamıştır (işlenenlerden hiçbiri kayan türlerden değil).|İntegral yükseltmeler işlenenler üzerinde aşağıdaki gibi gerçekleştirilir:<br /><br /> -Her iki işlenen türü ise `unsigned` **uzun**, diğer işlenenin türü dönüştürülüp `unsigned long`.<br />-Eğer koşul önceki değil karşılanır ve her iki işlenen türü ise **uzun** ve diğer tür `unsigned` `int`, her iki işlenen türü için dönüştürülür `unsigned long`.<br />-Önceki iki koşul karşılanmazsa ve her iki işlenen türü ise **uzun**, diğer işlenenin türü dönüştürülüp **uzun**.<br />-Yukarıdaki üç koşullar karşılanmazsa ve her iki işlenen türü ise `unsigned int`, diğer işlenenin türü dönüştürülüp `unsigned int`.<br />-Yukarıdaki koşullar hiçbiri karşılanıyorsa, her iki işlenen türü için dönüştürülür `int`.|  
  
 Aşağıdaki kodda, tabloda açıklanan dönüştürme kuralları gösterilmektedir:  
  
```  
  
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
  
 Yukarıdaki örnekte bulunan ilk deyim, iki integral türü olan `iVal` ve `ulVal`'ın çarpımını göstermektedir. Sağlanan koşul, iki işlenenin de kayan türden olmaması ve bir işlenenin `unsigned int` türünden olmasıdır. Bu nedenle, diğer işlenen `iVal`, `unsigned int` türüne dönüştürülür. Sonuç `dVal`'a atanır. Yerine bir işlenen türüdür durumdur **çift**; bu nedenle, `unsigned int` Çarpım sonucunu yazmak için dönüştürülür **çift**.  
  
 Önceki örnekte ikinci ifade eklenmesi gösterilmektedir bir **float** ve bir tam sayı türü `fVal` ve `ulVal`. `ulVal` Değişken türü için dönüştürülür **float** (tabloda üçüncü koşul). Toplamın sonucunu yazmak için dönüştürülür **çift** (ikinci tablodaki koşul) ve atanan `dVal`.  
  
## <a name="pointer-conversions"></a>İşaretçi dönüşümleri  
 İşaretçiler atama, başlatma, karşılaştırma ve diğer ifadeler sırasında dönüştürülebilir.  
  
### <a name="pointer-to-classes"></a>İşaretçi sınıfları  
 İçinde bir sınıf için bir işaretçi bir taban sınıfı için bir işaretçi dönüştürülebilir iki durumlar vardır.  
  
 İlk olarak belirtilen temel sınıf erişilebilir olduğunda ve dönüştürme anlaşılır olur. (Bkz [birden çok taban sınıfı](../cpp/multiple-base-classes.md) belirsiz temel sınıf başvurular hakkında daha fazla bilgi için.)  
  
 Bir taban sınıf erişilebilir olup türetme içinde kullanılan devralma tür bağlıdır. Aşağıdaki çizimde gösterilen devralma göz önünde bulundurun.  
  
 ![Temel gösteren Devralma Grafiği&#45;sınıf erişilebilirlik](../cpp/media/vc38xa1.gif "vc38XA1")  
Devralma Grafiği için temel sınıf erişilebilirlik çizimi  
  
 Aşağıdaki tabloda görüldüğü durum için temel sınıf erişilebilirlik gösterir.  
  
### <a name="base-class-accessibility"></a>Taban sınıfı erişilebilirlik  
  
|İşlev türü|Türetme|Dönüştürme<br /><br /> B * a\* yasal?|  
|----------------------|----------------|-------------------------------------------|  
|Dış (değil sınıf kapsamlı) işlevi|Özel|Hayır|  
||Korumalı|Hayır|  
||Ortak|Evet|  
|B üye işlevi (kapsamdaki B)|Özel|Evet|  
||Korumalı|Evet|  
||Ortak|Evet|  
|C üye işlevi (C kapsamdaki)|Özel|Hayır|  
||Korumalı|Evet|  
||Ortak|Evet|  
  
 Bir açık tür dönüştürme kullandığınızda, bir sınıf için bir işaretçi bir taban sınıfı için bir işaretçi dönüştürülebilir ikinci bir durumdur. (Bkz [açık tür dönüşümleri ifadelerle](http://msdn.microsoft.com/en-us/060ad6b4-9592-4f3e-8509-a20ac84a85ae) açık tür dönüştürme hakkında daha fazla bilgi için.)  
  
 Bu tür dönüştürme "alt nesne," temel sınıfı tarafından tamamen açıklanan nesne kısmı için bir işaretçi sonucudur.  
  
 Aşağıdaki kod iki sınıf tanımlar `A` ve `B`, burada `B` türetildiği `A`. (Devralma hakkında daha fazla bilgi için bkz: [türetilmiş sınıfları](../cpp/inheritance-cpp.md).) Ardından tanımlar `bObject`, bir nesne türü `B`ve iki işaretçiler (`pA` ve `pB`) nesnesine gelin.  
  
```  
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
  
 İşaretçinin `pA` türü `A *`, hangi yorumlayabilir anlamı "türünde bir nesne işaretçisi `A`." Üyeleri `bObject` `(`gibi `BComponent` ve `BMemberFunc`) türü için benzersiz olan `B` ve bu nedenle aracılığıyla erişilemeyen `pA`. `pA` İşaretçi sınıfında tanımlanan yalnızca bu (üye işlevleri ve veri) nesnesinin özelliklerini erişim sağlayan `A`.  
  
### <a name="pointer-to-function"></a>İşlev işaretçisi  
 Bir işlev işaretçisi türüne dönüştürülebilir **void \*** , türü **void \***  bu işaretçiyi tutmak için yeterince büyük değil.  
  
### <a name="pointer-to-void"></a>Void işaretçi  
 Türü için işaretçileri `void` herhangi bir türü, ancak yalnızca bir açık tür dönüştürme işaretçilere dönüştürülebilir (aksine c). (Bkz [açık tür dönüşümleri ifadelerle](http://msdn.microsoft.com/en-us/060ad6b4-9592-4f3e-8509-a20ac84a85ae) tür atamaları hakkında daha fazla bilgi için.) Herhangi bir tür için bir işaretçi bir işaretçi türü örtük olarak dönüştürülebilir `void`. Tamamlanmamış bir nesne türü için bir işaretçi bir işaretçi dönüştürülebilir `void` (örtük) ve (açıkça) yedekleyin. Bu tür bir dönüştürme sonucu özgün işaretçi değerine eşittir. Bir nesne, bildirilmiş ancak boyutu veya temel sınıf belirlemek kullanılabilir yeterli bilgi tamamlanmamış olarak kabul edilir.  
  
 Değil herhangi bir nesne için bir işaretçi **const** veya `volatile` gösteren bir işaretçi türü örtük olarak dönüştürülebilir **void \*** .  
  
### <a name="const-and-volatile-pointers"></a>const ve volatile işaretçiler  
 C++ Standart dönüştürme sağlamıyorsa bir **const** veya `volatile` türü değil bir türe **const** veya `volatile`. Ancak, herhangi bir tür dönüştürme (güvensiz dönüşümlerini dahil) açık tür atamaları kullanılarak belirtilebilir.  
  
> [!NOTE]
>  Statik üye işaretçileri dışındaki üye C++ işaretçileri normal işaretçilerini farklı ve aynı standart dönüşümler sahip değil. Statik üye işaretçileri normal işaretçiler ve normal işaretçileri olarak aynı dönüştürmeleri vardır.   
  
### <a name="null-pointer-conversions"></a>null işaretçi dönüşümleri  
 Sıfır olarak değerlendirilir bir tam sayı sabit ifadesi veya bir işaretçi, türe bu tür bir ifade "null işaretçinin." olarak adlandırılan bir işaretçi dönüştürülür Bu işaretçinin, herhangi bir geçerli nesne veya işlevin işaretçisiyle eşit olmayacak şekilde değerlendirileceği garanti edilir (aynı uzaklığa sahip olan, ancak farklı nesnelere işaret edebilen işaretçi tabanlı nesneler dışında).  
  
 C ++ 11 [nullptr](../cpp/nullptr.md) türü C türü null işaretçinin tercih edilen.  
  
### <a name="pointer-expression-conversions"></a>İşaretçi ifade dönüşümleri  
 Dizi türündeki bir ifade, aynı türden bir işaretçiye dönüştürülebilir. Dönüştürme işleminin sonucunda, ilk dizi öğesinin işaretçisi elde edilir. Aşağıdaki örnekte, böyle bir dönüştürme gösterilmektedir:  
  
```  
char szPath[_MAX_PATH]; // Array of type char.  
char *pszPath = szPath; // Equals &szPath[0].  
```  
  
 Belirli bir türü döndüren bir işlevle sonuçlanan ifade, aşağıdakiler haricinde bu türü döndüren bir işlevin işaretçisine dönüştürülür:  
  
-   Address-of işleci için işlenen olarak ifade kullanılır (**&**).  
  
-   İfade, işlev çağrısı işlecinin bir işleneni olarak kullanılıyorsa.  
  
## <a name="reference-conversions"></a>Başvuru dönüşümleri  
 Bir sınıf için bir başvuru aşağıdaki durumlarda bir temel sınıf için bir başvuruya dönüştürülebilir:  
  
-   Belirtilen taban sınıfı erişilebilir.  
  
-   Dönüştürme belirsiz değildir. (Bkz [birden çok taban sınıfı](../cpp/multiple-base-classes.md) belirsiz temel sınıf başvurular hakkında daha fazla bilgi için.)  
  
 Dönüştürmenin sonucu temel sınıfı temsil eden alt nesne için bir işaretçidir.  
  
## <a name="pointer-to-member"></a>İşaretçiden üyeye  
 Sınıf üyeleri için işaretçiler; atama, başlatma, karşılaştırma ve diğer ifadeler sırasında dönüştürülebilir. Bu bölüm aşağıdaki üye işaretçisi dönüştürmelerini açıklar:  
  
## <a name="pointer-to-base-class-member"></a>Taban sınıf üyesi işaretçi  
 Aşağıdaki koşullar karşılandığında, temel sınıfın üyesinin işaretçisi sınıfın kendisinden üretilmiş üyesinin işaretçisine dönüştürülebilir:  
  
-   Türetilmiş sınıfın işaretçisinden temel sınıf işaretçisine ters dönüştürme erişilebilirdir.  
  
-   Türetilmiş sınıf, neredeyse temel sınıftan devralmaz.  
  
 Sol işlenen üyenin bir işaretçisi olduğunda, sağ işlenen üye işaretçisi türünde veya 0 olarak değerlendirilen sabit bir ifade olmalıdır. Bu atama, yalnızca aşağıdaki durumlarda geçerlidir:  
  
-   Sağ işlenen, sol işlenenle aynı sınıfta olan üyenin bir işaretçisidir.  
  
-   Sol işlenen, sağ işlenenin sınıfından genel ve açık olarak türetilmiş sınıfın üyesinin bir işaretçisidir.  
  
## <a name="integral-constant-conversions"></a>Tamsayı sabit dönüşümleri  
 Sıfır olarak değerlendirilen bir integral sabiti ifadesi, "null işaretçi" adı verilen bir işaretçiye dönüştürülür. Bu işaretçinin, herhangi bir geçerli nesne veya işlevin işaretçisiyle eşit olmayacak şekilde değerlendirileceği garanti edilir (aynı uzaklığa sahip olan, ancak farklı nesnelere işaret edebilen işaretçi tabanlı nesneler dışında).  
  
 Aşağıdaki kodda, `i` sınıfındaki `A` üyesinin işaretçisinin tanımı gösterilmektedir. `pai` işaretçisi, null işaretçi olan 0 ile başlatılır.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)