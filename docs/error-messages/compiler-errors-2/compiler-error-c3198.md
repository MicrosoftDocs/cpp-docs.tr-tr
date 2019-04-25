---
title: Derleyici Hatası C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 61a3d14f9ad47edaa1e9b9f2b25d38b8dae7165c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243231"
---
# <a name="compiler-error-c3198"></a>Derleyici Hatası C3198

kayan noktalı pragmaların geçersiz kullanımı: fenv_access pragma yalnızca hassas modda çalışır

[fenv_access](../../preprocessor/fenv-access.md) pragma altında kullanıldı bir [/FP](../../build/reference/fp-specify-floating-point-behavior.md) dışında ayarlama **/FP: precise**.

Aşağıdaki örnek, C3198 oluşturur:

```
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```