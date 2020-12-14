---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2802'
title: Derleyici hatası C2802
ms.date: 11/04/2016
f1_keywords:
- C2802
helpviewer_keywords:
- C2802
ms.assetid: 08b68c0e-9382-40ac-8949-39a7a2749e05
ms.openlocfilehash: ff526306b89a5679147a30e7b3cd2f07ddc2b8f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297453"
---
# <a name="compiler-error-c2802"></a>Derleyici hatası C2802

' işleç işleci ' statik üyesinin hiç biçimsel parametresi yok

Üye işlevi tarafından tanımlanan bir işlecin **`static`** en az bir parametresi olmalıdır.

Aşağıdaki örnek C2802 oluşturur:

```cpp
// C2802.cpp
// compile with: /clr /c
ref class A {
   static operator+ ();   // C2802
   static operator+ (A^, A^);   // OK
};
```
