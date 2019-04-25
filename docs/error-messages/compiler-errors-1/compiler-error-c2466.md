---
title: Derleyici Hatası C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: 516f9b024947e0100a753e4e010a5b51b1fb24a1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62230535"
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