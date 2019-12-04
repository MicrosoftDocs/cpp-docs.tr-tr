---
title: Derleyici hatası C3363
ms.date: 11/04/2016
f1_keywords:
- C3363
helpviewer_keywords:
- C3363
ms.assetid: 41aa922f-608e-4f7a-ba66-451fc1161935
ms.openlocfilehash: 44b41dd706c7eb290c71d7312464d688cbcf08d3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757364"
---
# <a name="compiler-error-c3363"></a>Derleyici hatası C3363

' Type ': ' TypeId ' yalnızca bir türe uygulanabilir

[TypeId](../../extensions/typeid-cpp-component-extensions.md) işleci yanlış kullanıldı.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3363 oluşturur.

```cpp
// C3363.cpp
// compile with: /clr
int main() {
   System::typeid;   // C3363
}
```
