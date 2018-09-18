---
title: Derleyici Hatası C2466 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2466
dev_langs:
- C++
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8d43ee9d09fba77db022177a06c6ebe95c65ff79
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037846"
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