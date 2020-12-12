---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2292'
title: Derleyici hatası C2292
ms.date: 11/04/2016
f1_keywords:
- C2292
helpviewer_keywords:
- C2292
ms.assetid: 256b392f-2b8f-4162-b578-e7633984e162
ms.openlocfilehash: fb3630edc1aa3fc3aeb1b90d3ab79b17c775fa61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268255"
---
# <a name="compiler-error-c2292"></a>Derleyici hatası C2292

' tanımlayıcı ': en iyi durum devralma gösterimi: ' representation1 ' tanımlanmış, ancak ' representation2 ' gerekli

Şu kodun [/VMB](../../build/reference/vmb-vmg-representation-method.md) ile derlenmesi ("en iyi durum her zaman" temsili) C2292 neden olur.

```cpp
// C2292.cpp
// compile with: /vmb
class __single_inheritance X;

struct A { };
struct B { };
struct X : A, B { };  // C2292, X uses multiple inheritance
```
