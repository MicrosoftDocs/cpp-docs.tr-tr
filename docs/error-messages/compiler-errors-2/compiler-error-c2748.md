---
title: Derleyici hatası C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: e43defbf28c76dadcc7921ca76778413c41490a6
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759639"
---
# <a name="compiler-error-c2748"></a>Derleyici hatası C2748

yönetilen veya WinRT dizisi oluşturma, dizi boyutuna veya dizi başlatıcısına sahip olmalıdır

Yönetilen veya WinRT dizisi hatalı biçimlendirilmiş. Daha fazla bilgi için bkz. [dizi](../../extensions/arrays-cpp-component-extensions.md).

Aşağıdaki örnek C2748 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2748.cpp
// compile with: /clr
int main() {
   array<int> ^p1 = new array<int>();   // C2748
   // try the following line instead
   array<int> ^p2 = new array<int>(2);
}
```
