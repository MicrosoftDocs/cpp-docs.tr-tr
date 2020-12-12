---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2) C4396'
title: Derleyici Uyarısı (düzey 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: ab8743c748044456fa1826c805f8d652d76c403d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173525"
---
# <a name="compiler-warning-level-2-c4396"></a>Derleyici Uyarısı (düzey 2) C4396

"ad": bir friend bildirimi bir işlev şablonunun bir özelleştirmesine başvurduğunda satır içi tanımlayıcı kullanılamaz

Bir işlev şablonunun özelleştirmesi [satır içi](../../cpp/inline-functions-cpp.md) belirticilerden herhangi birini belirtemez. Derleyici uyarı C4396 ' i yayınlar ve satır içi belirleyicisi yoksayar.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- **`inline`** **`__inline`** **`__forceinline`** Friend işlevi bildiriminden, veya belirticisini kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, tanımlayıcı ile geçersiz bir Friend işlevi bildirimi gösterir **`inline`** .

```cpp
// C4396.cpp
// compile with: /W2 /c

class X;
template<class T> void Func(T t, int i);

class X {
    friend inline void Func<char>(char t, int i);  //C4396
// try the following line instead
//    friend void Func<char>(char t, int i);
    int i;
};
```
