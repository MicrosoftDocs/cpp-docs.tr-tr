---
title: Derleyici Hatası C3366 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3366
dev_langs:
- C++
helpviewer_keywords:
- C3366
ms.assetid: efc55bcf-c16d-43c1-a36f-87a6165fa2a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b3638ba2415839c044d9a82d82d0abe8bc2c98e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026510"
---
# <a name="compiler-error-c3366"></a>Derleyici Hatası C3366

'variable': statik veri üyeleri, yönetilen veya WinRTtypes sınıf tanımının içinde tanımlanmalıdır

Bir WinRT ya da .NET sınıf veya arabirim dışında sınıf veya arabirim tanımı statik üyesi başvuru çalışıldı.

Derleyici, tam sınıfının tanımı, (meta verileri tek seferde sonra yaymak üzere) bilmesi gerekir ve statik veri üyeleri sınıf içinde başlatılacak gerektirir.

Örneğin, aşağıdaki örnekte C3366 oluşturur ve bu sorunun nasıl gösterir:

```
// C3366.cpp
// compile with: /clr /c
ref class X {
   public:
   static int i;   // initialize i here to avoid C3366
};

int X::i = 5;      // C3366
```
