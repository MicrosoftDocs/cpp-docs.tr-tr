---
title: "anahtar sözcüğü otomatik | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: auto_cpp
dev_langs: C++
helpviewer_keywords:
- automatic storage class [C++], auto keyword
- auto keyword [C++]
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21b2155ffd5bb3861202c112bd9552ed36113a02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Anahtar sözcükler](../cpp/keywords-cpp.md)