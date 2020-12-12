---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4550'
title: Derleyici Uyarısı (düzey 1) C4550
ms.date: 11/04/2016
f1_keywords:
- C4550
helpviewer_keywords:
- C4550
ms.assetid: f902b4ed-5f17-48ea-b693-92f4fb8c8054
ms.openlocfilehash: 8edb7744f522312933bcf9d273982e591918dac2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265980"
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
