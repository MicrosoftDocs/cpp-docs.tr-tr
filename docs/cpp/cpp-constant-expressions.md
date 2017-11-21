---
title: C++ sabit ifadeleri | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f6961e210af254cd807b133e034610f03ca866e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="c-constant-expressions"></a>C++ Sabit İfadeleri
A *sabit* değer değişmez bir olduğundan. C++, nesnenin değiştirilmesi ve o hedefi zorlamak için tasarlanmamıştır hedefi express sağlamak için iki anahtar sağlar.  
  
 C++ sabit ifadeleri gerektirir — bir sabite değerlendirmek ifadeleri — bildirimlerini için:  
  
-   Dizi sınırları  
  
-   Seçici içindeki case deyimleri  
  
-   Bit alan uzunluğu belirtimi  
  
-   Numaralandırma başlatıcıları  
  
 Sabit ifadeler yasal yalnızca işlenenler şunlardır:  
  
-   Sabit değerler  
  
-   Numaralandırma sabitleri  
  
-   Sabit ifadeler ile başlatılmış değerleri const olarak bildirilen  
  
-   `sizeof`ifadeler  
  
 Nonintegral Sabitleri (açık veya örtülü olarak) bir sabit ifadesine yasal olarak tam sayı türleri dönüştürülmelidir. Bu nedenle, aşağıdaki kodu uygundur:  
  
```  
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
 Açık dönüşümler tam sayı türleri için sabit ifadeler yasal; diğer tüm türleri ve türetilmiş türler için işlenen olarak kullanılması dışında geçersiz `sizeof` işleci.  
  
 Virgül işleci ve atama işleçleri sabit ifadelerinde kullanılamaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İfade türleri](../cpp/types-of-expressions.md)