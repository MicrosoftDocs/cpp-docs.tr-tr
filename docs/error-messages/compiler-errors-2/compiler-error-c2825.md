---
title: Derleyici hatası C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: 6a51901477958056356a96d71adde4241d60a2ac
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750591"
---
# <a name="compiler-error-c2825"></a>Derleyici hatası C2825

var: arkasından ':: ' geldiğinde bir sınıf veya ad alanı olmalıdır

Nitelikli bir ad oluşturmak için başarısız bir girişimde bulunuldu.

Örneğin, kodunuzun işlev adının şununla başladığı bir işlev bildirimi içermediğinden emin olun::.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2825 oluşturur:

```cpp
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```
