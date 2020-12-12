---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4688'
title: Derleyici Uyarısı (düzey 1) C4688
ms.date: 11/04/2016
f1_keywords:
- C4688
helpviewer_keywords:
- C4688
ms.assetid: a027df3c-b2b8-4c49-8539-c2bc42db74e8
ms.openlocfilehash: 9abd793463cf576549b09a1a887d225317ca6fc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97285168"
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
