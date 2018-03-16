---
title: Tek boyutlu diziler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 033d772a40ddf55474ca845c9c5708423bcf5e90
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2018
---
# <a name="one-dimensional-arrays"></a>Bir Boyutlu Diziler
Köşeli ayraçlar içinde bir ifade arkasından bir sonek ifadesi (**[]**) bir dizi nesnesi bir öğenin alt gösterimidir. Alt simge ifadesi adresini değerinde temsil eden *ifade* ötesinde konumlandırır *sonek ifade* olarak ifade edilen zaman  
  
```  
  
postfix-expression  
[  
expression  
]  
  
```  
  
 Genellikle, tarafından temsil edilen değer *sonek ifade* bir dizi tanımlayıcı gibi bir işaretçi değeri ve *ifade* bir tamsayı değeri. Ancak, tüm sözdizimsel olarak olduğundan bu ifadelerden biri işaretçi türü ve diğer tamsayı türünde olması gereklidir. Bu nedenle tam sayı değeri olabilir. *sonek ifade* konumu ve işaretçi değeri parantez içinde olabilir *ifade*, veya "alt simge," konum. Örneğin, bu kodu yasal verilmiştir:  
  
```  
// one_dimensional_arrays.c  
int sum, *ptr, a[10];  
int main() {  
   ptr = a;  
   sum = 4[ptr];  
}  
```  
  
 Alt simge ifadeleri genellikle dizi öğelerine başvurmak için kullanılır, ancak bir işaretçi bir alt simge uygulayabilirsiniz. Hangi değerlerin sırasını, *ifade* parantez içine alınmalıdır (**[]**).  
  
 Alt simge ifadesi işaretçi değeri tam sayı değeri eklemek ve ardından yönlendirme işleci uygulama değerlendirilir (**\***) sonucu. (Bkz [yöneltmesi ve adresi işleçlerin](../c-language/indirection-and-address-of-operators.md) indirection işleci Tartışması için.) Tek boyutlu dizi için aşağıdaki dört ifadeleri eşdeğer olduğunu varsayarak uygulamada `a` gösteren bir işaretçidir ve `b` bir tamsayıdır:  
  
```  
a[b]  
*(a + b)  
*(b + a)  
b[a]  
```  
  
 Toplama işleci dönüştürme kurallarına göre (içinde verilen [ADDITIVE işleçleri](../c-language/c-additive-operators.md)), tam sayı değeri bir adres uzaklık işaretçi ele türün çarparak dönüştürülür.  
  
 Örneğin, tanımlayıcı varsayalım `line` için bir dizi başvuruyor `int` değerleri. Alt simge ifadesi değerlendirmek için aşağıdaki yordamı kullanılan `line[ i ]`:  
  
1.  Tamsayı değeri `i` uzunluğu tanımlanan bayt sayısı ile çarpılır bir `int` öğesi. Dönüştürülmüş değeri `i` temsil eden `i` `int` konumlar.  
  
2.  Bu dönüştürülen değer özgün işaretçi değeri eklenir (`line`) uzaklığını bir adresi elde etmek üzere `i` `int` gelen konumlandırır `line`.  
  
3.  İndirection işleci yeni adresine uygulanır. Bu konumda dizi öğesinin değeri sonucudur (sezgisel, `line [ i ]`).  
  
 Alt simge ifadesi `line[0]` tarafından temsil edilen adres uzaklığı itibaren satırının ilk öğe değerini temsil eden `line` 0'dır. Benzer şekilde, bir ifade gibi `line[5]` satır öğesi uzaklığı beş konumdan veya dizinin altıncı öğesine başvuruyor.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alt Simge İşleci:](../cpp/subscript-operator.md)