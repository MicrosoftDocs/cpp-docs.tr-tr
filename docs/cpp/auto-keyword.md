---
title: auto anahtar sözcüğü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a02ed2a19f44f19396038f8e41cb1c7f5a069407
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405892"
---
# <a name="auto-keyword"></a>auto Anahtar Sözcüğü
**Otomatik** anahtar sözcüğü, bir bildirim belirticisidir. Ancak, C++ standardı bu anahtar sözcük için özgün ve düzeltilmiş bir anlamı tanımlar. Visual C++ 2010 önce **otomatik** anahtar sözcüğü bir değişken bildirir *otomatik* depolama sınıfı; diğer bir deyişle, yerel kullanım ömrüne sahip bir değişken. Visual C++ 2010 ile başlayarak **otomatik** anahtar sözcüğü, türü atanan bildiriminden başlatma ifadesinden bir değişken bildirir. [/Zc:auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği anlamını denetler **otomatik** anahtar sözcüğü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
auto declarator ;  
auto declarator initializer;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tanımı **otomatik** anahtar sözcüğü değişiklikleri C++ programlama dilinde, ancak C programlama dilini içinde değil.  
  
 Aşağıdaki konularda açıklanmıştır **otomatik** anahtar sözcüğü ve karşılık gelen derleyici seçeneği:  
  
-   [Otomatik](../cpp/auto-cpp.md) yeni tanımını açıklar **otomatik** anahtar sözcüğü.  
  
-   [/ZC:Auto (değişken türünü türet)](../build/reference/zc-auto-deduce-variable-type.md) hangi tanımının derleyiciye bildiren derleyici seçeneğini açıklar **otomatik** anahtar sözcüğünü kullanın.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)