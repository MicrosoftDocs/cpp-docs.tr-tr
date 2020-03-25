---
title: Derleyici Uyarısı (düzey 1 ve düzey 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 7ce8b3242def187e4b8b442f403f92f013a9ca6e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164787"
---
# <a name="compiler-warning-level-1-and-level-4-c4949"></a>Derleyici Uyarısı (düzey 1 ve düzey 4) C4949

' Managed ' ve ' yönetilmeyen ' pragmaları yalnızca '/CLR [: Option] ' ile derlendikleri zaman anlamlıdır

Kaynak kodu [/clr](../../build/reference/clr-common-language-runtime-compilation.md)ile derlenmediğinde, derleyici [yönetilen](../../preprocessor/managed-unmanaged.md) ve yönetilmeyen pragmaları yoksayar. Bu uyarı bilgilendirme amaçlıdır.

Aşağıdaki örnek C4949 oluşturur:

```cpp
// C4949.cpp
// compile with: /LD /W1
#pragma managed   // C4949
```

**#Pragma** , **/clr**olmadan kullanıldığında, C4949 4. düzey bir uyarıdır.

Aşağıdaki örnek C4949 oluşturur:

```cpp
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```
