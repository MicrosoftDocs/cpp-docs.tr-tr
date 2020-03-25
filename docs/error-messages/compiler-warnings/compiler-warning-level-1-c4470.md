---
title: Derleyici Uyarısı (düzey 1) C4470
ms.date: 11/04/2016
f1_keywords:
- C4470
helpviewer_keywords:
- C4470
ms.assetid: f52a3eaa-a235-4747-a47d-9ec4ad4cb0ea
ms.openlocfilehash: 164bc1fa85466b80ee66a22a1a1679a40b89ce2e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186731"
---
# <a name="compiler-warning-level-1-c4470"></a>Derleyici Uyarısı (düzey 1) C4470

kayan nokta denetimi pragmaları/clr altında yoksayılır

Kayan denetim pragmaları:

- [fenv_access](../../preprocessor/fenv-access.md)

- [float_control](../../preprocessor/float-control.md)

- [fp_contract](../../preprocessor/fp-contract.md)

[/clr](../../build/reference/clr-common-language-runtime-compilation.md)altında hiçbir etkisi yoktur.

Aşağıdaki örnek C4470 oluşturur:

```cpp
// C4470.cpp
// compile with: /clr /W1 /LD
#pragma float_control(except, on)   // C4470
```
