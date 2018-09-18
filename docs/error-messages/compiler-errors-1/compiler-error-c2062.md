---
title: Derleyici Hatası C2062 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2062
dev_langs:
- C++
helpviewer_keywords:
- C2062
ms.assetid: 6cc98353-2ddf-43ab-88a2-9cc91cdd6033
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbda0894b25e09681207d6447bb40727d490fc02
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072257"
---
# <a name="compiler-error-c2062"></a>Derleyici Hatası C2062

türü 'type' beklenmeyen

Derleyici, bir tür adı beklenmiyordu.

Aşağıdaki örnek, C2062 oluşturur:

```
// C2062.cpp
// compile with: /c
struct A {  : int l; };   // C2062
struct B { private: int l; };   // OK
```

C2062 tanıtıcıları tanımlanmamış bir oluşturucunun parametre listesi türlerinde derleyici yöntemi nedeniyle ortaya çıkabilir. Derleyici tanımlanmamış bir (yazılmış?) türü karşılaşırsa, oluşturucu bir ifade ve C2062 sorunları varsayar. Çözümlemek için yalnızca bir oluşturucu parametre listesinde tanımlı türleri kullanın.