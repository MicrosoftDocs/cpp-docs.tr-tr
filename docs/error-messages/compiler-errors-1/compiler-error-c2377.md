---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2377'
title: Derleyici hatası C2377
ms.date: 11/04/2016
f1_keywords:
- C2377
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
ms.openlocfilehash: 727472410bea0db9f837388956e8af5c9a8433d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174747"
---
# <a name="compiler-error-c2377"></a>Derleyici hatası C2377

' tanımlayıcı ': yeniden tanımlama; TypeDef başka bir simgeyle aşırı yüklenemez

**`typedef`** Tanımlayıcı yeniden tanımlandı.

Aşağıdaki örnek C2377 oluşturur:

```cpp
// C2377.cpp
// compile with: /c
typedef int i;
int i;   // C2377
int j;   // OK
```
