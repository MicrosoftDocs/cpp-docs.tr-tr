---
title: Önemli hata C1190 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1190
dev_langs:
- C++
helpviewer_keywords:
- C1190
ms.assetid: dee2266d-6c40-4f6e-91db-f01e65f8d2bc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96e1ab464199466a5df13362f40ac9143be49a68
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46084958"
---
# <a name="fatal-error-c1190"></a>Önemli hata C1190

Yönetilen hedeflenen kod gerektiren bir ' / clr' seçeneği

CLR yapıları kullanıyor, ancak sizin belirtmediğiniz **/CLR**.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

Aşağıdaki örnek, C1190 oluşturur:

```
// C1190.cpp
// compile with: /c
__gc class A {};   // C1190
ref class A {};
```