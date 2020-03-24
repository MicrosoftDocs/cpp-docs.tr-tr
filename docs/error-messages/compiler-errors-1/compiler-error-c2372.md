---
title: Derleyici hatası C2372
ms.date: 03/23/2020
f1_keywords:
- C2372
helpviewer_keywords:
- C2372
ms.assetid: 406bea63-c8d3-4231-9d26-c70af6980840
ms.openlocfilehash: 4d60f93def9bfe8359496803c8aede1ec698b465
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150946"
---
# <a name="compiler-error-c2372"></a>Derleyici hatası C2372

> '*tanımlayıcı*': yeniden tanımlama; farklı yöneltme türleri

Tanımlayıcı, farklı bir türetilmiş türle zaten tanımlanmış.

Aşağıdaki örnek C2372 oluşturur:

```cpp
// C2372.cpp
// compile with: /c
extern int *fp;
extern int fp[];   // C2372
extern int fp2[];   // OK
```
