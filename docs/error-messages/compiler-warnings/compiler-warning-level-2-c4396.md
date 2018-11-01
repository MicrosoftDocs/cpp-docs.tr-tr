---
title: Derleyici Uyarısı (Düzey 2) C4396
ms.date: 11/04/2016
f1_keywords:
- C4396
helpviewer_keywords:
- C4396
ms.assetid: 7cd6b283-db17-4574-b299-03e0b913ad70
ms.openlocfilehash: 84045ea2c285be8b1c1c9d1fd62b417db00dd29c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445324"
---
# <a name="compiler-warning-level-2-c4396"></a>Derleyici Uyarısı (Düzey 2) C4396

"name": işlev şablonunun bir özelleştirmesi için bir friend bildirimi başvurduğunda, satır içi belirtici kullanılamaz

Herhangi bir işlev şablonunun bir özelleştirmesi belirtemezsiniz [satır içi](../../cpp/inline-functions-cpp.md) tanımlayıcıları. Derleyici Uyarısı C4396 sorunları ve satır içi belirticiyi yok sayar.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

- Kaldırma `inline`, `__inline`, veya `__forceinline` belirticisi arkadaş işlev bildirimi öğesinden.

## <a name="example"></a>Örnek

Geçersiz bir arkadaş işlev bildirimi ile aşağıdaki kod örnekte gösterildiği bir `inline` tanımlayıcısı.

```
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