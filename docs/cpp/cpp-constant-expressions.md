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
ms.workload: cplusplus
ms.openlocfilehash: 0cd30dd51b3d87b7d82b917734d187ae2278837a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [İfade Türleri](../cpp/types-of-expressions.md)