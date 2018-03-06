---
title: "anahtar sözcüğü otomatik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 48c21ec8304fa5c56bb29f07eea4bec169fbda83
ms.sourcegitcommit: 4e01d36ffa64ea11bacf589f79d2f1df947e2510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/05/2018
---
# <a name="auto-keyword"></a>auto Anahtar Sözcüğü
`auto` anahtar sözcüğü bir bildirim belirticisidir. Ancak, C++ standardı bu anahtar sözcük için özgün ve düzeltilmiş bir anlamı tanımlar. Visual C++ 2010 önce `auto` anahtar sözcüğü bir değişkende bildirir *otomatik* depolama sınıfı; yani, yerel bir ömre sahip bir değişken. Visual C++ 2010 ile başlayan `auto` anahtar sözcüğü bildiriminden başlatma ifadesinden türü anlaşılan bir değişken bildirir. [/Zc:auto &#91;-&#93;](../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği denetimleri anlamını `auto` anahtar sözcüğü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 `auto` anahtar sözcüğünün tanımını, C++ programlama dilinde değişir, ancak C programlama dilinde değişmez.  
  
 Aşağıdaki konularda, `auto` anahtar sözcüğü ve karşılık gelen derleyici seçeneği açıklanmaktadır:  
  
-   [Otomatik](../cpp/auto-cpp.md) yeni tanımı açıklar `auto` anahtar sözcüğü.  
  
  
-   [/ZC:Auto (değişken türünü)](../build/reference/zc-auto-deduce-variable-type.md) derleyici hangi tanımını söyler derleyici seçeneği açıklanmıştır `auto` kullanmak üzere anahtar sözcük.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)