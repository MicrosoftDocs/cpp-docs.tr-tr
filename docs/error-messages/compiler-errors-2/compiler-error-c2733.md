---
title: Derleyici Hatası C2733 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2733
dev_langs:
- C++
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 42749c26f4a8a474f3dac076b80a1bfe71e89d58
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110451"
---
# <a name="compiler-error-c2733"></a>Derleyici Hatası C2733

'function' izin aşırı yüklü işlevin ikinci C bağlaması

Birden fazla aşırı yüklenmiş işlev C bağlaması ile bildirilir. C bağlaması kullanırken, belirtilen işlevinin yalnızca bir form dış olabilir. Aşırı yüklenmiş işlevler ve aynı ada sahip olduğundan, C programları ile kullanılamaz.

Aşağıdaki örnek, C2733 oluşturur:

```
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```