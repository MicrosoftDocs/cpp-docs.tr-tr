---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2825'
title: Derleyici hatası C2825
ms.date: 11/04/2016
f1_keywords:
- C2825
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
ms.openlocfilehash: fa72f915a77ec26e6da402ae8ff87ee380f1838c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194585"
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
