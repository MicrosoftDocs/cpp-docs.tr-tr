---
title: C işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ternary operators
- operators [C]
- symbols, operators
- binary operators
- associativity of operators
- binary data, binary expressions
ms.assetid: 13bc4c8e-2dc9-4b23-9f3a-25064e8777ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9f90f25d52a2555eb92938dd29ebb7e5bfc6e96a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="c-operators"></a>C İşleçleri
C işleçleri alt kümesi olan [C++ yerleşik işleçleri](../cpp/cpp-built-in-operators-precedence-and-associativity.md).  
  
 Üç tür işleç vardır. Tekli ifade, işlenenin önüne eklenmiş bir tekli işleç veya arkasından bir ifade gelen `sizeof` anahtar sözcüğünden oluşur. İfade, değişkenin adı veya atama ifadesi olabilir. İfade atama ifadesiyse, parantez içine alınmalıdır. İkili ifade, ikili işleç tarafından birleştirilmiş iki işlenenden oluşur. Üçlü ifade, koşullu ifade işleci tarafından birleştirilmiş üç işlenenden oluşur.  
  
 C, aşağıdaki tekli işleçler içerir:  
  
|Simgesi|Ad|  
|------------|----------|  
|**- ~ !**|Olumsuzlaştırma ve tamamlayıcı işleçleri|  
|**\* &**|Yöneltme ve adres işleçleri|  
|`sizeof`|Boyut işleci|  
|**+**|Tekli artı işleci|  
|**++ --**|Tekli artırma ve azaltma işleçleri|  
  
 Soldan sağa ilişkilendirilen ikili işleçler. C, aşağıdaki ikili işleçleri sağlar:  
  
|Simgesi|Ad|  
|------------|----------|  
|**\* / %**|Çarpma işleçleri|  
|**+ -**|Toplama işleçleri|  
|**<\< >>**|Kaydırma işleçleri|  
|**\<   >   \<=   >=   ==   !=**|İlişkisel işleçler|  
|**&   &#124; ^**|Bit düzeyinde işleçler|  
|**&&   &#124;&#124;**|Mantıksal işleçler|  
|**,**|Sıralı değerlendirme işleci|  
  
 Temel işleci (**: >**), Microsoft 16 bit C Derleyici önceki sürümleri tarafından desteklenen, açıklanan [C dili sözdizimi özeti](../c-language/c-language-syntax-summary.md).  
  
 Koşullu ifade işleci, ikili ifadelere göre daha düşük önceliğe sahiptir ve sağla ilişkilendirilebilir olduğu için onlardan farklıdır.  
  
 İşleçlere sahip ifadeler, tekli veya ikili atama işleçleri kullanan atama ifadeleri de içerir. Birli atama işleçleri artışı olan (`++`) ve azaltma (**--**) işleçleri; ikili atama işleçleri olan basit atama işleci (**=**) ve bileşik atama işleçleri. Her bileşik atama işleci, başka bir ikili işlecin basit atama işleciyle birleşiminden oluşur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfadeler ve Atamalar](../c-language/expressions-and-assignments.md)