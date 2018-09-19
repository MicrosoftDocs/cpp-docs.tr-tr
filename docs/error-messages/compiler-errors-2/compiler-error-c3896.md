---
title: Derleyici Hatası C3896 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3896
dev_langs:
- C++
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6714d356fa2f09bdfce2750ff31432b5b4e14461
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109736"
---
# <a name="compiler-error-c3896"></a>Derleyici Hatası C3896

'member': hatalı Başlatıcı: Bu sabit değerli veri üyesi yalnızca 'nullptr' ile başlatılabilir

A [değişmez değer](../../windows/literal-cpp-component-extensions.md) veri üyesi başlatılan yanlış.  Bkz: [nullptr](../../windows/nullptr-cpp-component-extensions.md) daha fazla bilgi için.

Aşağıdaki örnek, C3896 oluşturur:

```
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```