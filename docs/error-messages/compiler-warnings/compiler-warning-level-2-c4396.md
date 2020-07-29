---
title: Derleyici Uyarısı (düzey 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: fec6875fdb2e8a60e71fe08da1ed4e8fa82e4641
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87206048"
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
