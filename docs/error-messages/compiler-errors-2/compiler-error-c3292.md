---
title: Derleyici Hatası C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: a68d3e922532480063fe4c294e40f453885743e8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62222636"
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