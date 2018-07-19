---
title: C++ sabit ifadeleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fef56154f34f645b279ffccd99915d366388cb06
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026708"
---
# <a name="c-constant-expressions"></a>C++ Sabit İfadeleri
A *sabit* değeri olan bir değişikliğe neden olmaz. C++ iki anahtar sözcüğü bir nesne değiştirilecek ve o hedefi zorlamak için tasarlanmamıştır hedefi express olanak sağlar.  
  
C++ sabit ifadeleri gerekir — bir sabit ifadeler — bildirimleri için:  
  
 -   Dizi sınırları  
      
 -   Case deyimleri Seçici  
      
 -   Bit alanı uzunluğu belirtimi  
      
 -   Sabit listesi başlatıcıları  
  
Sabit ifadelerde yasal yalnızca işlenen şunlardır:  
  
 -   Sabit değerler  
      
 -   Numaralandırma sabitlerini  
      
 -   Değerleri, sabit ifadeler başlatılır const olarak bildirildi  
      
 -   **sizeof** ifadeleri  
  
Nonintegral Sabitleri (açıkça veya dolaylı olarak) sabit bir ifadede meşru integral türlerine dönüştürülmesi gerekir. Bu nedenle, aşağıdaki kod geçerlidir:  
  
```cpp 
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
Açık dönüştürmeler integral türleri sabit ifadelerde geçerli; diğer tüm türleri ve türetilen türler için işlenen olarak kullanılması dışında geçersiz `sizeof` işleci.  
  
Virgül işleci ve atama işleçleri sabit ifadelerde kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade Türleri](../cpp/types-of-expressions.md)