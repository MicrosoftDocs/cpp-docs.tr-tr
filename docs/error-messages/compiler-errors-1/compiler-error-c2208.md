---
title: Derleyici Hatası C2208 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2208
dev_langs:
- C++
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6721166efad2fc214ccf2c2a45ec2342b67c39e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101728"
---
# <a name="compiler-error-c2208"></a>Derleyici Hatası C2208

'type': Bu tür kullanılarak tanımlanmış bir üye yok

İçin bir tür adı çözülürken bir tanımlayıcı, bir toplama bildiriminde olmakla birlikte derleyici üyesi bildiremezsiniz.

Aşağıdaki örnek, C2208 oluşturur:

```
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```