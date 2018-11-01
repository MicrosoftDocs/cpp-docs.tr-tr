---
title: Derleyici Hatası C2377
ms.date: 11/04/2016
f1_keywords:
- C2377
helpviewer_keywords:
- C2377
ms.assetid: f7660965-bf4c-4cd9-8307-1bd7016678a1
ms.openlocfilehash: b4789469fe27dafb2fb13bf3db085958db8d1478
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528771"
---
# <a name="compiler-error-c2377"></a>Derleyici Hatası C2377

'identifier': yeniden tanımlama; TypeDef başka herhangi bir simgeyle aşırı yüklenemez

A `typedef` tanımlayıcısı yeniden.

Aşağıdaki örnek, C2377 oluşturur:

```
// C2377.cpp
// compile with: /c
typedef int i;
int i;   // C2377
int j;   // OK
```