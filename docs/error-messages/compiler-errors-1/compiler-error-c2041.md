---
title: Derleyici Hatası C2041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2041
dev_langs:
- C++
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bee199ea3ddca7ae329fc17ed6c3c013dc460eb7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082176"
---
# <a name="compiler-error-c2041"></a>Derleyici Hatası C2041

'character' temel 'number' için geçersiz sayı

Belirtilen karakterin tabanı (örneğin, sekizlik veya onaltılık) için geçerli bir rakam değil.

Aşağıdaki örnek, C2041 oluşturur:

```
// C2041.cpp
int i = 081;   // C2041  8 is not a base 8 digit
```

Olası çözüm:

```
// C2041b.cpp
// compile with: /c
int j = 071;
```