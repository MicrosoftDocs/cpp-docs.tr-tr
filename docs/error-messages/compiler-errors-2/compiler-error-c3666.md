---
title: Derleyici Hatası C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: aba1d3dfcf620db0f1fbaf14d0fb01745ca82659
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50465552"
---
# <a name="compiler-error-c3666"></a>Derleyici Hatası C3666

'Oluşturucu': geçersiz kılma belirticisi 'anahtar sözcüğü bir oluşturucu üzerinde kullanılamaz'

Bir geçersiz kılma belirticisi bir oluşturucu kullanıldı ve bu izin verilmiyor. Daha fazla bilgi için [geçersiz kılma tanımlayıcıları](../../windows/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3666 oluşturur.

```
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```