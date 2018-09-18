---
title: Derleyici Hatası C3898 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3898
dev_langs:
- C++
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39fe816c2637df5e5a474718d70b404bbc0c2df6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030038"
---
# <a name="compiler-error-c3898"></a>Derleyici Hatası C3898

'var': tür veri üyeleri yalnızca yönetilen türlerin üyeleri olabilir

Bir [initonly](../../dotnet/initonly-cpp-cli.md) veri üyesi, bir yerel sınıf içinde bildirildi.  Bir `initonly` veri üyesi yalnızca bir CLR sınıfında bildirilebilir.

Aşağıdaki örnek, C3898 oluşturur:

```
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Olası çözüm:

```
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```