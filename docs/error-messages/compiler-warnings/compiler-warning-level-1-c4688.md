---
title: Derleyici Uyarısı (düzey 1) C4688
ms.date: 11/04/2016
f1_keywords:
- C4688
helpviewer_keywords:
- C4688
ms.assetid: a027df3c-b2b8-4c49-8539-c2bc42db74e8
ms.openlocfilehash: 1c94198eca0a88174c8655e0d571c37f82a2df36
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781971"
---
# <a name="compiler-warning-level-1-c4688"></a>Derleyici Uyarısı (düzey 1) C4688

'kısıtlaması': sınırlama listesi 'type' derleme özel türünü içeriyor

Bir kısıtlama listesi türü derlemenin dışından erişilebilir olduğunda yeniden kullanılabilir olmayacaktır yani bir derleme özel türünü içeriyor. Daha fazla bilgi için [genel türler](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4688 oluşturur.

```
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