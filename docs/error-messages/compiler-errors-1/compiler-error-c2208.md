---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2208'
title: Derleyici hatası C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 76452c504e5f90857b15c5fc9250923705d3d20c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245648"
---
# <a name="compiler-error-c2208"></a>Derleyici hatası C2208

' Type ': Bu tür kullanılarak tanımlı üye yok

Bir tür adına çözümleyen tanımlayıcı bir toplama bildiriminde, ancak derleyici bir üye bildiremez.

Aşağıdaki örnek C2208 oluşturur:

```cpp
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```
