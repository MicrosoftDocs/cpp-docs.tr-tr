---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1 ve düzey 4) C4949'
title: Derleyici Uyarısı (düzey 1 ve düzey 4) C4949
ms.date: 11/04/2016
f1_keywords:
- C4949
helpviewer_keywords:
- C4949
ms.assetid: 34f45a05-c115-49cb-9f67-0bd4f0735d9b
ms.openlocfilehash: 2330843c34207edbe99607208baff634836044cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336023"
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

**#Pragma** , **/clr** olmadan kullanıldığında, C4949 4. düzey bir uyarıdır.

Aşağıdaki örnek C4949 oluşturur:

```cpp
// C4949b.cpp
// compile with: /LD /W4
#pragma unmanaged   // C4949
```
