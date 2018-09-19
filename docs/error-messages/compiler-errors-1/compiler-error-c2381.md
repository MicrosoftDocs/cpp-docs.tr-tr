---
title: Derleyici Hatası C2381 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2381
dev_langs:
- C++
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f09cd8c16eeb5ec797643cb6653d069df41b136
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076950"
---
# <a name="compiler-error-c2381"></a>Derleyici Hatası C2381

'function': yeniden tanımlama; __declspec(noreturn) farklıdır

Bir işlev bildirildi ve kullanılan tanımı ardından tanımlanan [noreturn](../../cpp/noreturn.md) `__declspec` değiştiricisi. Kullanımını `noreturn` oluşturan bir işlevi yeniden tanımlama; bildirim ve tanım kullanımı üzerinde anlaşmaya varması gerekiyor `noreturn`.

Aşağıdaki örnek, C2381 oluşturur:

```
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```