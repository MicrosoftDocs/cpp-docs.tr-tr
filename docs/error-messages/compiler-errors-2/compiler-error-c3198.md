---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3198'
title: Derleyici hatası C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 8f72dd32af7f004696afd87b7141768f09ea5f12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321989"
---
# <a name="compiler-error-c3198"></a>Derleyici hatası C3198

kayan noktalı pragmaların geçersiz kullanımı: fenv_access pragma yalnızca hassas modda çalışır

[fenv_access](../../preprocessor/fenv-access.md) pragma, **/FP: kesin** dışında bir [/FP](../../build/reference/fp-specify-floating-point-behavior.md) ayarı altında kullanıldı.

Aşağıdaki örnek C3198 oluşturur:

```cpp
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```
