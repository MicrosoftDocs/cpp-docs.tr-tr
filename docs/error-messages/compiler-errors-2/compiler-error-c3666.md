---
title: Derleyici hatası C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: 990dea32b2928671f426235138698071fe038f63
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758157"
---
# <a name="compiler-error-c3666"></a>Derleyici hatası C3666

' constructor ': geçersiz kılma belirticisi ' anahtar sözcüğü ' bir Oluşturucu üzerinde kullanılamaz

Bir geçersiz kılma belirticisi bir Oluşturucu üzerinde kullanıldı ve buna izin verilmiyor. Daha fazla bilgi için bkz. [geçersiz kılma belirticileri](../../extensions/override-specifiers-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3666 oluşturur.

```cpp
// C3666.cpp
// compile with: /clr /c
ref struct R {
   R() new {}   // C3666
   R(int i) {}   // OK
};
```
