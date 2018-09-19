---
title: Derleyici Hatası C2507 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2507
dev_langs:
- C++
helpviewer_keywords:
- C2507
ms.assetid: f102aff5-de7d-4c3f-9cac-2ddf9ce02b14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16cc9c5f21618f3b681fbefbfadfd66b0219d5ac
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022727"
---
# <a name="compiler-error-c2507"></a>Derleyici Hatası C2507

'identifier': taban sınıfta çok fazla sayıda sanal değiştirici var

Bir sınıf veya yapı olarak bildirilir `virtual` birden çok kez. Yalnızca bir `virtual` değiştiricisi, her sınıf temel sınıf için bir liste görünebilir.

Aşağıdaki örnek, C2507 oluşturur:

```
// C2507.cpp
// compile with: /c
class A {};
class B : virtual virtual public A {};   // C2507
class C : virtual public A {};   // OK
```