---
title: "Yapı ve birleşim üyeleri | Microsoft Docs"
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
- member-selection operators
- structure members, referencing
- -> operator, structure and union members
- dot operator (.)
- referencing structure members
- . operator
- operators [C], member selection
- structure member selection
ms.assetid: bb1fe304-af49-4f98-808d-afdc99b3e319
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2183aead53ee02f36bc982e4f33ad174346da5f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="structure-and-union-members"></a>Yapı ve Birleşim Üyeleri
"Üye seçimi ifade" yapılar ve birleşimleri üyelerine başvuruyor. Bu tür bir ifade değeri ve seçilen üye türü vardır.  
  
```  
  
postfix-expression  
.  
identifier  
postfix-expression  
->  
identifier  
  
```  
  
 Bu liste, üye seçim ifadeleri iki tür açıklamaktadır:  
  
1.  İlk formunda *sonek ifade* bir değeri temsil eder `struct` veya **UNION** türü ve *tanımlayıcısı* belirtilen yapı veya birlik üyesi adları. İşlemi, değeri *tanımlayıcısı* ve bir l-değeri ise *sonek ifade* l-değeri. Bkz: [L-değeri ve r değeri ifadeleri](../c-language/l-value-and-r-value-expressions.md) daha fazla bilgi için.  
  
2.  İkinci formunda *sonek ifade* bir işaretçi bir yapı veya UNION, temsil eder ve *tanımlayıcısı* belirtilen yapı veya birlik üyesi adları. Değer budur *tanımlayıcısı* ve bir l-değeri.  
  
 Üye seçim ifadeleri iki tür benzer etkileri olabilir.  
  
 Aslında, üye seçimi işleci içeren bir ifade (**->**) süresi kullanan bir ifade kestirme sürümü (**.**) süre önce ifade oluşuyorsa indirection işleci (**\***) bir işaretçi değeri uygulanır. Bu nedenle,  
  
```  
  
expression  
->  
identifier  
  
```  
  
 eşdeğerdir  
  
```  
  
(*  
expression  
) .  
identifier  
  
```  
  
 zaman *ifade* bir işaretçi değerdir.  
  
## <a name="examples"></a>Örnekler  
 Aşağıdaki örnekler bu yapısı bildirimine bakın. İndirection işleci hakkında bilgi için (**\***) Bu örneklerde kullanılan, bkz: [yöneltmesi ve adresi işleçlerin](../c-language/indirection-and-address-of-operators.md).  
  
```  
struct pair   
{  
    int a;  
    int b;  
    struct pair *sp;  
} item, list[10];  
```  
  
 Üye seçim ifade için `item` yapısı şu şekilde görünür:  
  
```  
item.sp = &item;  
```  
  
 Adresini yukarıdaki örnekte `item` yapısı atanması `sp` yapısı üyesi. Bunun anlamı `item` kendisi için bir işaretçi içeriyor.  
  
```  
(item.sp)->a = 24;  
```  
  
 Bu örnekte, işaretçi ifade `item.sp` üye seçimi işleciyle kullanılan (**->**) üyesi için bir değer atamaya `a`.  
  
```  
list[8].b = 12;  
```  
  
 Bu bildirimi yapıları dizisinden bağımsız yapısı üye seçin gösterilmektedir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üye Erişim İşleçleri: . ve ->](../cpp/member-access-operators-dot-and.md)