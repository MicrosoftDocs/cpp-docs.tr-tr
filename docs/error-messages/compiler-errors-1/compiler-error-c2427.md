---
title: Derleyici Hatası C2427 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2427
dev_langs:
- C++
helpviewer_keywords:
- C2427
ms.assetid: a7d421af-6180-40b4-b7a6-9f3bc7dfaaf9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27d18dff26d98adb0dada58271c4ec20fde73755
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104796"
---
# <a name="compiler-error-c2427"></a>Derleyici Hatası C2427

'class': Bu kapsamda sınıf tanımlanamaz

İç içe geçmiş bir sınıf tanımlamak için bir girişimde bulunuldu, ancak iç içe geçmiş sınıf bir taban sınıfın en içeren sınıfın bir üyesidir.

Aşağıdaki örnek, C2427 oluşturur:

```
// C2427.cpp
// compile with: /c
template <class T>
struct S {
   struct Inner;
};

struct Y : S<int> {};

struct Y::Inner {};   // C2427

// OK
template<typename T>
struct S<T>::Inner {};
```