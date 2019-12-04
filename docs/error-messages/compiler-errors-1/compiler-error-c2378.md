---
title: Derleyici hatası C2378
ms.date: 11/04/2016
f1_keywords:
- C2378
helpviewer_keywords:
- C2378
ms.assetid: 507a91c6-ca72-48df-b3a4-2cf931c86806
ms.openlocfilehash: 63063ec98bbc4d42f3237fd42e42b9fdce489892
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745427"
---
# <a name="compiler-error-c2378"></a>Derleyici hatası C2378

' tanımlayıcı ': yeniden tanımlama; sembol, TypeDef ile aşırı yüklenemez

Tanımlayıcı bir `typedef`olarak yeniden tanımlandı.

Aşağıdaki örnek C2378 oluşturur:

```cpp
// C2378.cpp
// compile with: /c
int i;
typedef int i;   // C2378
typedef int b;   // OK
```
