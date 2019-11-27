---
title: Derleyici Uyarısı (düzey 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: 2f156bfbe92fbfb3437a7f0b9ac77a91976c2b1c
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189389"
---
# <a name="compiler-warning-level-3-c4646"></a>Derleyici Uyarısı (düzey 3) C4646

__declspec (noreturn) ile belirtilen işlevin void olmayan dönüş türü yok

[Noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisi ile işaretlenen bir işlev, [void](../../cpp/void-cpp.md) dönüş türüne sahip olmalıdır.

Aşağıdaki örnek C4646 oluşturur:

```cpp
// C4646.cpp
// compile with: /W3 /WX
int __declspec(noreturn) TestFunction()
{   // C4646  make return type void
}
```