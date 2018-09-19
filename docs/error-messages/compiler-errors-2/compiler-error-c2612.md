---
title: Derleyici Hatası C2612 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2612
dev_langs:
- C++
helpviewer_keywords:
- C2612
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2bdc91dd2b64c4fbd3a14670ba500ac970c9ad3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46135795"
---
# <a name="compiler-error-c2612"></a>Derleyici Hatası C2612

sondaki 'char' taban/üye Başlatıcı listesinde geçersiz

Bir karakter sonra son temel veya üye Başlatıcı listesinde görünür.

Aşağıdaki örnek, C2612 oluşturur:

```
// C2612.cpp
class A {
public:
   int i;
   A( int ia ) : i( ia ) + {};   // C2612
};
```