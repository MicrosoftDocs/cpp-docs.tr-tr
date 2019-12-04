---
title: Derleyici hatası C2854
ms.date: 11/04/2016
f1_keywords:
- C2854
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
ms.openlocfilehash: 70b763afa4d511823a62d4d3770fc030ab9fb2ec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745895"
---
# <a name="compiler-error-c2854"></a>Derleyici hatası C2854

#pragma hdrstop içinde sözdizimi hatası

`#pragma hdrstop` geçersiz bir dosya adı veriyor. Pragmaya, parantez ve tırnak işaretleri içinde isteğe bağlı bir dosya adı gelebilir:

Aşağıdaki örnek C2854 oluşturur:

```cpp
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```
