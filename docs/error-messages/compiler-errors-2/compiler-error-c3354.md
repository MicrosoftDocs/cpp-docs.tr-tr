---
title: Derleyici Hatası C3354
ms.date: 11/04/2016
f1_keywords:
- C3354
helpviewer_keywords:
- C3354
ms.assetid: 185de401-231e-4999-a149-172ee4c69d84
ms.openlocfilehash: 1ff2967f602722c99b58b679324bd4f50575f109
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523173"
---
# <a name="compiler-error-c3354"></a>Derleyici Hatası C3354

'function': temsilci oluşturmak için kullanılan işlev dönüş türü 'type' olamaz

Aşağıdaki türleri için dönüş türleri olarak geçersiz bir `delegate`:

- İşlev işaretçisi

- Üye işaretçisi

- Üye işlev işaretçisi

- Başvuru işlevi

- Üye işlev başvurusu

Aşağıdaki örnek, C3354 oluşturur:

```
// C3354_2.cpp
// compile with: /clr /c
using namespace System;
typedef void ( *VoidPfn )();

delegate VoidPfn func(); // C3354
// try the following line instead
// delegate  void func();
```
