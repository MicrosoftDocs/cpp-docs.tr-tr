---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3666'
title: Derleyici hatası C3666
ms.date: 11/04/2016
f1_keywords:
- C3666
helpviewer_keywords:
- C3666
ms.assetid: 459e51dd-cefb-4346-99b3-644f2d8b65b2
ms.openlocfilehash: 245fd061a7a1ce7b9b3e25ae76e6b15ec9428145
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134270"
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
