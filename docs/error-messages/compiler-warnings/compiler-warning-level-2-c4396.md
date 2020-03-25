---
title: Derleyici Uyarısı (düzey 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: f37fcc7ece09bb9028a522ec6baf85d0e0e585c2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161821"
---
# <a name="compiler-warning-level-2-c4396"></a>Derleyici Uyarısı (düzey 2) C4396

"ad": bir friend bildirimi bir işlev şablonunun bir özelleştirmesine başvurduğunda satır içi tanımlayıcı kullanılamaz

Bir işlev şablonunun özelleştirmesi [satır içi](../../cpp/inline-functions-cpp.md) belirticilerden herhangi birini belirtemez. Derleyici uyarı C4396 ' i yayınlar ve satır içi belirleyicisi yoksayar.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Friend işlevi bildiriminden `inline`, `__inline`veya `__forceinline` belirticisini kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, `inline` belirleyicisi ile geçersiz bir Friend işlevi bildirimi gösterir.

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
