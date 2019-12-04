---
title: Derleyici hatası C2466
ms.date: 11/04/2016
f1_keywords:
- C2466
helpviewer_keywords:
- C2466
ms.assetid: 75b251d1-7d0b-4a86-afca-26adedf74486
ms.openlocfilehash: aba4de518b9296fadc4746540e4e738c74908617
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743828"
---
# <a name="compiler-error-c2466"></a>Derleyici hatası C2466

sabit boyutu 0 olan bir dizi ayrılamaz

Bir dizi ayrılmış veya sıfır boyutuyla bildirilmiştir. Dizi boyutu için sabit ifade sıfırdan büyük bir tamsayı olmalıdır. Sıfır indisi olan bir dizi bildirimi yalnızca bir sınıf, yapı veya birleşim üyesi ve yalnızca Microsoft uzantıları ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) için geçerlidir.

Aşağıdaki örnek C2466 oluşturur:

```cpp
// C2466.cpp
// compile with: /c
int i[0];   // C2466
int j[1];   // OK
char *p;
```
