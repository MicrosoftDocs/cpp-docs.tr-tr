---
title: Derleyici Uyarısı (düzey 2 ve 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 9b6fb56045d53cd18689f3903bb3d7a08c3d4e4d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198010"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Derleyici Uyarısı (düzey 2 ve 3) C4008

' Identifier ': ' Attribute ' özniteliği yoksayıldı

Derleyici, bir işlev (düzey 3 uyarısı) veya veri (düzey 2 uyarısı) için `__fastcall`, **statik**veya **satır içi** özniteliği yoksaydı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. verilerle `__fastcall` özniteliği.

1. **Main** işlevi ile **statik** veya **satır içi** özniteliği.
