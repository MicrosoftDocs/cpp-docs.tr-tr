---
title: Derleyici Uyarısı (düzey 1 ve düzey 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: f2876813131271ebb2561f8ea7435bb96dc2ce17
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627410"
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