---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2748'
title: Derleyici hatası C2748
ms.date: 11/04/2016
f1_keywords:
- C2748
helpviewer_keywords:
- C2748
ms.assetid: b63ac78b-a200-499c-afea-15af1a1e819e
ms.openlocfilehash: 64720391906777ffd5f36c53e6f7ce27940426fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123025"
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
