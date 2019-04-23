---
title: Derleyici Hatası C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: edca117da585fee731041d696e05af1baf6d3e5c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776541"
---
# <a name="compiler-error-c3666"></a>Derleyici Hatası C3666

'Oluşturucu': geçersiz kılma belirticisi 'anahtar sözcüğü bir oluşturucu üzerinde kullanılamaz'

Bir geçersiz kılma belirticisi bir oluşturucu kullanıldı ve bu izin verilmiyor. Daha fazla bilgi için [geçersiz kılma tanımlayıcıları](../../extensions/override-specifiers-cpp-component-extensions.md).

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