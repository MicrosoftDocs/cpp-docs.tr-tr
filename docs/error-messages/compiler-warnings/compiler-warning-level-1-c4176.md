---
title: Derleyici Uyarısı (düzey 1) C4176
ms.date: 11/04/2016
f1_keywords:
- C4176
helpviewer_keywords:
- C4176
ms.assetid: cfffb934-219a-4a63-9df6-ba54405bf766
ms.openlocfilehash: 44f2dea9b5f0afb5b97867f9137f420ad92c388a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443127"
---
# <a name="compiler-warning-level-1-c4176"></a>Derleyici Uyarısı (düzey 1) C4176

'alt': #pragma bileşen tarayıcısı için Bilinmeyen alt bileşen

**Bileşen** pragması, geçersiz bir alt bileşen içeriyor. Belirli bir ad başvurularını tutmak için kullanmalısınız **başvuruları** adından önce seçeneği.

## <a name="example"></a>Örnek

```
// C4176.cpp
// compile with: /W1 /LD
#pragma component(browser, off, i)  // C4176
#pragma component(browser, off, references, i) // ok
```