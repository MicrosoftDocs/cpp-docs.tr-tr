---
title: Derleyici Hatası C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: a68d3e922532480063fe4c294e40f453885743e8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780658"
---
# <a name="compiler-error-c3292"></a>Derleyici Hatası C3292

cli ad alanı yeniden açılamıyor

Cli ad alanı, kodunuzda bildirilemez.  Daha fazla bilgi için [Platform, varsayılan ve cli ad alanları](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3292 oluşturur.

```
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```