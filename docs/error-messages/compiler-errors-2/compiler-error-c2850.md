---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2850'
title: Derleyici hatası C2850
ms.date: 11/04/2016
f1_keywords:
- C2850
helpviewer_keywords:
- C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
ms.openlocfilehash: 820aa0e12db5ffe7e6d7b7bf0e87282f53e8477c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260169"
---
# <a name="compiler-error-c2850"></a>Derleyici hatası C2850

' yapı ': yalnızca dosya kapsamında izin verilir; iç içe bir yapı içinde yer alamaz

Bazı pragmalar gibi yapılar yalnızca genel kapsamda yer alabilir.

Aşağıdaki örnek C2850 oluşturur:

```cpp
// C2850.cpp
// compile with: /c /Yc
// try the following line instead
// #pragma hdrstop
namespace X {
   #pragma hdrstop   // C2850
};
```
