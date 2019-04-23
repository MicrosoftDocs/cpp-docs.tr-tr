---
title: Derleyici Hatası C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: a68d3e922532480063fe4c294e40f453885743e8
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777009"
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