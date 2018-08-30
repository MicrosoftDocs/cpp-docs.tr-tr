---
title: Bir boyutlu diziler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], arrays
- one-dimensional arrays
- arrays [C++], one-dimensional
- square brackets [ ]
- square brackets [ ], arrays
- subscript expressions
ms.assetid: e28536e5-3b77-46b5-97fd-9b938c771816
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bbb47eae81df8b1080480843bfa5a444f6eb989f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196982"
---
# <a name="one-dimensional-arrays"></a>Bir Boyutlu Diziler
Köşeli ayraçlar içinde bir ifade arkasından bir sonek ifadesi (**[]**) bir öğenin bir dizi nesnesinin simgeli gösterimidir. Alt simge ifadesi adresi değeri temsil eden *ifade* ötesinde konumlandırır *sonek ifadesi* olarak ifade edilen zaman  
  
```  
postfix-expression [ expression ]
```  
  
 Genellikle, tarafından temsil edilen değeri *sonek ifadesi* bir işaretçi değeri, bir dizi tanımlayıcısına gibi ve *ifade* bir integral değeridir. Ancak, tüm sözdizimsel olarak olan bir ifadenin bir işaretçi türünde olması ve diğeri Tamsayı türünde olması gereklidir. Tamsayı değeri bu nedenle olabilir *sonek ifadesi* konumu ve işaretçi değeri parantez içinde olabilir *ifade*, veya "alt simge," konum. Örneğin, bu yasal kodudur:  
  
```  
// one_dimensional_arrays.c  
int sum, *ptr, a[10];  
int main() {  
   ptr = a;  
   sum = 4[ptr];  
}  
```  
  
 Alt simge ifadeleri genellikle dizi öğelerine başvurmak için kullanılan, ancak herhangi bir işaretçiye bir alt simge uygulayabilirsiniz. Hangi değerleri sırasını *ifade* ayraçlar içine alınmalıdır (**[]**).  
  
 Alt simge ifadesi tam sayı değeri işaretçi değerine ekleyerek ve ardından yöneltme işlecini değerlendirilir (<strong>\*</strong>) sonucu. (Bkz [yöneltme ve adres işleçleri](../c-language/indirection-and-address-of-operators.md) yöneltme işlecinin bir tartışma.) Aslında, tek boyutlu bir dizi için aşağıdaki dört eşdeğer olduğunu varsayarak ifadelerdir `a` gösteren bir işaretçidir ve `b` bir tamsayıdır:  
  
```  
a[b]  
*(a + b)  
*(b + a)  
b[a]  
```  
  
 Toplama işleci dönüştürme kurallarına göre (içinde verilen [toplama işleçleri](../c-language/c-additive-operators.md)), tamsayı değeri, işaretçi tarafından ele alınan uzunluğunu çarpılmasıyla adresi uzaklık dönüştürülür.  
  
 Örneğin, tanımlayıcı varsayalım `line` dizilerine başvuruyor `int` değerleri. Alt simge ifadesi değerlendirmek için aşağıdaki yordamı kullanılan `line[ i ]`:  
  
1.  Tamsayı değeri `i` uzunluğu tanımlanan bayt sayısı çarpılır bir `int` öğesi. Dönüştürülmüş değeri `i` temsil `i` `int` konumları.  
  
2.  Dönüştürülen bu değer, orijinal işaretçi değerine eklenir (`line`) uzaklığını adresin elde etmek üzere `i` `int` gelen konumlandırır `line`.  
  
3.  Yöneltme işleci yeni adresine uygulanır. Bu konumda dizi öğesinin değeri sonucudur (sezgisel, `line [ i ]`).  
  
 Alt simge ifadesi `line[0]` satırının ilk öğenin değeri tarafından temsil edilen adrese uzaklığı beri temsil eden `line` 0'dır. Benzer şekilde, bir ifade gibi `line[5]` satır öğesi uzaklığı beş konumdan veya dizinin altıncı öğesinin anlamına gelir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alt Simge İşleci:](../cpp/subscript-operator.md)