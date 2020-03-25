---
title: Derleyici Uyarısı (düzey 1) C4550
ms.date: 11/04/2016
f1_keywords:
- C4550
helpviewer_keywords:
- C4550
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
ms.openlocfilehash: 454b0154f555ef1ba1ac13ea7a87d454d59c6f05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186172"
---
# <a name="compiler-warning-level-1-c4550"></a>Derleyici Uyarısı (düzey 1) C4550

ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerlendirilir

Bir işleve başvuru yapılan bir işaretçiye bir bağımsız değişken listesi eksik.

## <a name="example"></a>Örnek

```cpp
// C4550.cpp
// compile with: /W1
bool f()
{
   return true;
}

typedef bool (*pf_t)();

int main()
{
   pf_t pf = f;
   if (*pf) {}  // C4550
   return 0;
}
```
