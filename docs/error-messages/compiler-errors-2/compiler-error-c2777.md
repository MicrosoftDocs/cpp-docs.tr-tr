---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2777'
title: Derleyici hatası C2777
ms.date: 11/04/2016
f1_keywords:
- C2777
helpviewer_keywords:
- C2777
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
ms.openlocfilehash: 301dadd8a62826455c0cdd7b7d9d8d9d3832d666
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298129"
---
# <a name="compiler-error-c2777"></a>Derleyici hatası C2777

her özellik için yalnızca bir ' Put ' yöntemi belirtilebilir

[Property](../../cpp/property-cpp.md) declspec değiştiricisi birden fazla `put` özelliğe sahip.

Aşağıdaki örnek C2777 oluşturur:

```cpp
// C2777.cpp
struct A {
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777
   // try the following line instead
   // __declspec(property(put=PutProp))
      int prop;
   int PutProp(void);
   int PutPropToo(void);
};
```
