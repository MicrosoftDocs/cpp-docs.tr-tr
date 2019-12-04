---
title: Derleyici hatası C3153
ms.date: 11/04/2016
f1_keywords:
- C3153
helpviewer_keywords:
- C3153
ms.assetid: d775d97e-2480-484f-81f1-88406b10f947
ms.openlocfilehash: 54fa7de8eb3df8d4b3695544c5285cc202275492
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745926"
---
# <a name="compiler-error-c3153"></a>Derleyici hatası C3153

' interface ': bir arabirimin örneğini oluşturamazsınız

Arabirim örneği oluşturulamıyor. Bir arabirimin üyelerini kullanmak için arabiriminden bir sınıf türetirsiniz, arabirim üyelerini uygulayın ve ardından üyeleri kullanın.

Aşağıdaki örnek C3153 oluşturur:

```cpp
// C3153.cpp
// compile with: /clr
interface class A {
};

int main() {
   A^ a = gcnew A;   // C3153
}
```
