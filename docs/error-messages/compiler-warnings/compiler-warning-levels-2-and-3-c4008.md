---
title: Derleyici Uyarısı (düzey 2 ve 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: ab51b16331cc6a102c828234d2c2b8be84f2d276
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225247"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Derleyici Uyarısı (düzey 2 ve 3) C4008

' Identifier ': ' Attribute ' özniteliği yoksayıldı

Derleyici **`__fastcall`** , **`static`** **`inline`** bir işlev (düzey 3 uyarısı) veya veri (düzey 2 uyarısı) için, veya özniteliğini yok sayıldı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. **`__fastcall`** verileri olan öznitelik.

1. **`static`** ya da **`inline`** **Main** işlevi olan özniteliği.
