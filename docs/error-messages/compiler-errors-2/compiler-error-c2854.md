---
title: Derleyici Hatası C2854 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2854
dev_langs:
- C++
helpviewer_keywords:
- C2854
ms.assetid: 917fec9c-790a-4149-8dfc-00d17a09199c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bd49c9fbfa88667cdb2e8bd57466632c0a051e3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074818"
---
# <a name="compiler-error-c2854"></a>Derleyici Hatası C2854

#pragma hdrstop içinde sözdizimi hatası

`#pragma hdrstop` Geçersiz dosya adı sağlar. Pragma, parantezleri ve tırnak işaretleri içinde isteğe bağlı bir dosya adı tarafından izlenebilir:

Aşağıdaki örnek, C2854 oluşturur:

```
// C2854.cpp
// compile with: /c
#pragma hdrstop( "\\source\\pchfiles\\myheader.pch" ]   // C2854
// try the following line instead
// #pragma hdrstop( "\\source\\pchfiles\\myheader.pch" )
```