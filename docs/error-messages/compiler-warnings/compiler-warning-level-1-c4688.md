---
title: Derleyici Uyarısı (düzey 1) C4688
ms.date: 11/04/2016
f1_keywords:
- C4688
helpviewer_keywords:
- C4688
ms.assetid: a027df3c-b2b8-4c49-8539-c2bc42db74e8
ms.openlocfilehash: bc869b7e22bc8bce0230892dc9a67d6aaec09f46
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052510"
---
# <a name="compiler-warning-level-1-c4688"></a>Derleyici Uyarısı (düzey 1) C4688

' Constraint ': kısıtlama listesi ' Type ' derleme özel türünü içeriyor

Bir kısıtlama listesinin bütünleştirilmiş kod özel türü vardır, yani tür derlemenin dışından erişildiğinde kullanılabilir olmaz. Daha fazla bilgi için bkz. [Genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4688 oluşturur.

```cpp
// C4688.cpp
// compile with: /clr /c /W1
ref struct A {};   // private type
public ref struct B {};

// Delete the following 3 lines to resolve.
generic <class T>
where T : A   // C4688
public ref struct M {};

generic <class T>
where T : B
public ref struct N {};
```