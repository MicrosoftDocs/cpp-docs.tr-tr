---
title: Derleyici Hatası C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 516f9b024947e0100a753e4e010a5b51b1fb24a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50526373"
---
# <a name="compiler-error-c2466"></a>Derleyici Hatası C2466

sabit boyutu 0 olan bir dizi tahsis edilemiyor

Bir dizi tahsis veya boyutu sıfır. Dizi boyutu için sabit ifade, sıfırdan büyük bir tamsayı olmalıdır. Bir sıfır alt simge ile bir dizi bildirimi yalnızca bir sınıf, yapı veya birleşim üyesi için ve yalnızca Microsoft uzantılı yasal ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)).

Aşağıdaki örnek, C2466 oluşturur:

```
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```