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
ms.openlocfilehash: 06a07c9d37994b4214da9b2eb53d02104525d7c4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408118"
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
  
Açık dönüştürmeler integral türleri sabit ifadelerde geçerli; diğer tüm türleri ve türetilen türler için işlenen olarak kullanılması dışında geçersiz **sizeof** işleci.  
  
Virgül işleci ve atama işleçleri sabit ifadelerde kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İfade Türleri](../cpp/types-of-expressions.md)