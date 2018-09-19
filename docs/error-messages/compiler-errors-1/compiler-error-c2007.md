---
title: Derleyici Hatası C2007 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2007
dev_langs:
- C++
helpviewer_keywords:
- C2007
ms.assetid: ecd09d99-5036-408b-9e46-bc15488f049e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2ac9383b144496228038529808e24dfd1c0f7a1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097334"
---
# <a name="compiler-error-c2007"></a>Derleyici Hatası C2007

\#söz dizimi tanımlayın

Hiçbir tanımlayıcı sonra görünen bir `#define`. Hatayı gidermek için bir tanımlayıcı kullanın.

Aşağıdaki örnek, C2007 oluşturur:

```
// C2007.cpp
#define   // C2007
```

Olası çözüm:

```
// C2007b.cpp
// compile with: /c
#define true 1
```