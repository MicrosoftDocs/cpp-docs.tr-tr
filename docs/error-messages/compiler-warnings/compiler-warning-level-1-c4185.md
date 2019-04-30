---
title: Derleyici Uyarısı (düzey 1) C4185
ms.date: 11/04/2016
f1_keywords:
- C4185
helpviewer_keywords:
- C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
ms.openlocfilehash: c4cabeb206da8da9f9157a8f8eee65c1894ce024
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391614"
---
# <a name="compiler-warning-level-1-c4185"></a>Derleyici Uyarısı (düzey 1) C4185

'attribute' Bilinmeyen #import özniteliği yoksayılıyor

Öznitelik, geçerli bir öznitelik değil `#import`. Yoksayılır.

## <a name="example"></a>Örnek

```
// C4185.cpp
// compile with: /W1 /c
#import "stdole2.tlb" no_such_attribute   // C4185
```