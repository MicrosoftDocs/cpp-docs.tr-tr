---
title: İfade semantikleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- grammar, expressions
- expressions [C++], semantics
- expression evaluation
- expression evaluation, about expression evaluation
ms.assetid: 4a792154-533b-48b9-8709-31bfc170f0a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8419ea4e446c8bf2f555c680079ccb91cc26afb5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="semantics-of-expressions"></a>İfade Semantikleri
İfadeler, işleçlerinin önceliğine ve gruplandırılmasına göre değerlendirilir. ([İşleç önceliği ve birleşim](../cpp/cpp-built-in-operators-precedence-and-associativity.md) içinde [sözcük kuralları](../cpp/lexical-conventions.md), işleçler zorunlu tuttukları ifadeleri C++ ilişkileri gösterir.)  
  
## <a name="order-of-evaluation"></a>Değerlendirme sırası  
 Bu örneği göz önünde bulundurun:  
  
```cpp  
// Order_of_Evaluation.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main()  
{  
    int a = 2, b = 4, c = 9;  
  
    cout << a + b * c << "\n";  
    cout << a + (b * c) << "\n";  
    cout << (a + b) * c << "\n";  
}  
```  
  
```Output  
38  
38  
54  
```  
  
 ![Bir ifade değerlendirme sırayla](../cpp/media/vc38zv1.gif "vc38ZV1")  
İfade-Değerlendirme Sırası  
  
 Yukarıdaki şekilde gösterilen ifadenin değerlendirilme sırası, işleçlerin öncelik ve birleşimlerine göre belirlenir:  
  
1.  Çarpma (*), bu ifadede en yüksek önceliğe sahiptir; bu yüzden `b * c` alt ifadesi ilk olarak değerlendirilir.  
  
2.  Toplama (+), sıradaki en yüksek önceliğe sahiptir, dolayısıyla `a` ve `b` ürününe `c` eklenir.  
  
3.  Sola kaydırma (<<), ifadedeki en düşük önceliğe sahiptir, ancak iki kez vardır. Sola kaydırma işleci soldan sağa doğru gruplama yaptığından, ilk önce sol alt ifade, ardından sağdaki değerlendirilir.  
  
 Alt ifadeleri gruplamak için parantez kullanıldığında, aşağıdaki şekilde gösterildiği gibi önceliği ve ayrıca ifadenin değerlendirilme sırasını değiştirir.  
  
 ![Değerlendirme sırası parantez ifadenin](../cpp/media/vc38zv2.gif "vc38ZV2")  
Parantezli İfade-Değerlendirme Sırası  
  
 Yukarıdaki şekildeki gibi ifadeler yalnızca yan etkileri için (bu örnekte bilgileri standart çıktı cihazına aktarmak için) değerlendirilir.  
  
## <a name="notation-in-expressions"></a>İfadelerdeki gösterim  
 C++ dili belirli uyumluluğunu işlenenler belirtirken belirtir. Aşağıdaki tabloda işlenenler türlerini kabul edilebilir türündeki işlenenler gerektiren işleçleri gösterilmektedir *türü*.  
  
### <a name="operand-types-acceptable-to-operators"></a>İşlenen türleri işleçleri için kabul edilebilir  
  
|Türü bekleniyor|İzin verilen türleri|  
|-------------------|-------------------|  
|*Türü*|`const` *Türü*<br /> `volatile` *Türü*<br /> *Türü*&<br /> `const` *Türü*&<br /> `volatile` *Türü*&<br /> `volatile const` *Türü*<br /> `volatile const` *Türü*&|  
|*Türü*\*|*Türü*\*<br /> `const` *Türü*\*<br /> `volatile` *Türü*\*<br /> `volatile const` *Türü*\*|  
|`const` *Türü*|*Türü*<br /> `const` *Türü*<br />`const` *Türü*&|  
|`volatile` *Türü*|*Türü*<br /> `volatile` *Türü*<br /> `volatile` *Türü*&|  
  
 Önceki kuralları birlikte her zaman kullanılabilir olmadığından geçici bir nesne için sabit bir işaretçi bir işaretçi beklenirken sağlanabilir.  
  
## <a name="ambiguous-expressions"></a>Belirsiz ifadeler  
 Belirli ifadelerin anlamları içinde belirsiz. Bir nesnenin değeri birden çok kez aynı ifadesinde değişiklik yapıldığında bu deyimler en sık oluşur. Bu ifadeler burada dili bir tanımlamıyor değerlendirme belirli bir sıraya bağlıdır. Aşağıdaki örnek göz önünde bulundurun:  
  
```  
int i = 7;  
  
func( i, ++i );  
```  
  
 C++ dili, bir işlev çağrısı için bağımsız değişkenler değerlendirilme sırasını garanti etmez. Bu nedenle, önceki örnekte, `func` parametreleri soldan sağa veya sağdan sola değerlendirilir bağlı olarak değerleri 7 ve 8 veya 8 ve 8 kendi parametreleri için alabilir.  
  
## <a name="c-sequence-points-microsoft-specific"></a>C++ sıralama noktaları (Microsoft Specific)  
 Bir ifade, bir nesnenin değerini ardışık "dizi noktaları" arasında yalnızca bir kez değiştirebilir.  
  
 C++ dili tanımı şu anda dizi noktaları belirtmemektedir. Microsoft C++, C işleçleri içeren ve aşırı yüklenmiş işleçler içermeyen tüm ifadeler için ANSI C ile aynı dizi noktalarını kullanır. İşleçler aşırı yüklendiğinde, semantikler işleç sıralamasından işlev çağrısı sıralamasına dönüşür. Microsoft C++ aşağıdaki dizi noktalarını kullanır:  
  
-   Mantıksal AND işlecinin sol işleneni (&&). Mantıksal AND işlecinin sol işleneni, tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır. Mantıksal AND işlecinin sağ işleneninin değerlendirileceği kesin değildir.  
  
-   Sol işleneni mantıksal OR işleci (&#124;&#124;). Mantıksal OR işlecinin sol işleneni, tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır. Mantıksal OR işlecinin sağ işleneninin değerlendirileceği kesin değildir.  
  
-   Virgül işlecinin sol işleneni. Virgül işlecinin sol işleneni tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır. Virgül işlecinin her iki işleneni de her zaman değerlendirilir.  
  
-   İşlev çağrısı işleci. İşlev çağrısı ifadesi ve işlevin varsayılan bağımsız değişkenler de dahil tüm bağımsız değişkenleri değerlendirilir ve işleve giriş yapılmadan önce tüm yan etkiler tamamlanır. Bağımsız değişkenler veya işlev çağrısı ifadesi arasında belirli bir değerlendirme sırası yoktur.  
  
-   Koşullu işlecin ilk işleneni. Koşullu işlecin ilk işleneni tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır.  
  
-   Bir bildirim deyiminde başlatmanın sonu gibi bir tam başlatma ifadesinin sonu.  
  
-   Bir ifade deyimindeki ifade. İfade deyimleri, sırasıyla isteğe bağlı bir ifadeden ve noktalı virgülden (;) oluşur. İfade, yan etkilere karşı tamamen değerlendirilir.  
  
-   Bir seçme (if veya switch) deyimindeki denetim ifadesi. İfade tamamen değerlendirilir ve seçime bağlı kod yürütülmeden önce tüm yan etkiler tamamlanır.  
  
-   While veya do deyiminin denetim ifadesi. İfade tamamen değerlendirilir ve while veya do döngüsünün sonraki yinelemesinde yer alan herhangi bir deyim yürütülmeden önce tüm yan etkiler tamamlanır.  
  
-   For deyiminin üç ifadesinden her biri. Her ifade tamamen değerlendirilir ve sonraki ifadeye geçilmeden önce tüm yan etkiler tamamlanır.  
  
-   Dönüş deyimindeki ifade. İfade tamamen değerlendirilir ve denetim çağırma işlevine dönmeden önce tüm yan etkiler tamamlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfadeler](../cpp/expressions-cpp.md)