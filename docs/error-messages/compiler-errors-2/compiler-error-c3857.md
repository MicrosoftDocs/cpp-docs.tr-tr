---
title: Derleyici Hatası C3857 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3857
dev_langs:
- C++
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 279ed343b57380df9db9180aa475e4d77ddf5ae5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097607"
---
# <a name="compiler-error-c3857"></a>Derleyici Hatası C3857

'type': birden çok tür parametre listeleri izin verilmez

Bir şablon büyük veya genel verilmeyen aynı türü için belirtildi.

Aşağıdaki örnek, C3857 oluşturur:

```
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

Olası çözüm:

```
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857, genel türler kullanırken da meydana gelebilir:

```
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

Olası çözüm:

```
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```