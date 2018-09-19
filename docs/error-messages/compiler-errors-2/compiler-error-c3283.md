---
title: Derleyici Hatası C3283 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3283
dev_langs:
- C++
helpviewer_keywords:
- C3283
ms.assetid: c51d912c-cde3-4928-904e-26734c8954ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0feaad0e0eb1b9dc5ee6c5b2f47e8f2a425b6d99
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096476"
---
# <a name="compiler-error-c3283"></a>Derleyici Hatası C3283

'type': arabirimin örnek oluşturucusu olamaz

Bir CLR [arabirimi](../../windows/interface-class-cpp-component-extensions.md) örnek oluşturucusu olamaz.  Statik Oluşturucu izin verilir.

Aşağıdaki örnek, C3283 oluşturur:

```
// C3283.cpp
// compile with: /clr
interface class I {
   I();   // C3283
};
```

Olası çözüm:

```
// C3283b.cpp
// compile with: /clr /c
interface class I {
   static I(){}
};
```