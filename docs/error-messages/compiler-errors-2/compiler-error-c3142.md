---
title: Derleyici Hatası C3142
ms.date: 11/04/2016
f1_keywords:
- C3142
helpviewer_keywords:
- C3142
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
ms.openlocfilehash: 38bf40b6e1b7495232d7c33317408b872081e9f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50446184"
---
# <a name="compiler-error-c3142"></a>Derleyici Hatası C3142

'property_name': bir özelliğin adresini alamazsınız

Bir özelliğin adresini geliştiriciler için kullanılabilir değil.

Aşağıdaki örnek, C3142 oluşturur:

```
// C3142_2.cpp
// compile with: /clr
using namespace System;
ref class CSize {
private:
   property int Size {
      int get();
   }
};

int main() {
    &CSize::Size; // C3142
}
```
