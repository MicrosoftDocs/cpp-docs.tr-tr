---
title: Derleyici hatası C2861
ms.date: 11/04/2016
f1_keywords:
- C2861
helpviewer_keywords:
- C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
ms.openlocfilehash: 3d6cab186d4acf229a32620f33c9c86e807459dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751995"
---
# <a name="compiler-error-c2861"></a>Derleyici hatası C2861

' işlev adı ': bir arabirim üye işlevi tanımlanamıyor

Derleyici arabirim anahtar sözcüğüyle karşılaştı veya bir yapıyı arabirim olarak çıkardığından bir üye işlev tanımı buldu.  Arabirim, üye işlevi için bir tanım içeremez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2861 oluşturur:

```cpp
// C2861.cpp
// compile with: /c
#include <objbase.h>   // required for IUnknown definition
[ object, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IMyInterface : IUnknown {
   HRESULT mf(int a);
};

HRESULT IMyInterface::mf(int a) {}   // C2861
```
