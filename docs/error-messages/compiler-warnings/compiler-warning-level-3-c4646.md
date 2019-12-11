---
title: Derleyici Uyarısı (düzey 3) C4646
ms.date: 11/04/2016
f1_keywords:
- C4646
helpviewer_keywords:
- C4646
ms.assetid: 23677e8e-603e-40e0-b99a-2e4894a1278e
ms.openlocfilehash: a5f78a978baa1c5b4c7854692d7b8b6ff294f3a2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991726"
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
