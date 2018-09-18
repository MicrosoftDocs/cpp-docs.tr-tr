---
title: Derleyici Hatası C2194 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2194
dev_langs:
- C++
helpviewer_keywords:
- C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6270835b75181abcc683ac8d625d6d9236ae2b95
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46035805"
---
# <a name="compiler-error-c2194"></a>Derleyici Hatası C2194

'identifier': bir metin kesimi

`data_seg` Pragma ile kullanılan bir segment adı kullanan `code_seg`.

Aşağıdaki örnek, C2194 oluşturur:

```
// C2194.cpp
// compile with: /c
#pragma code_seg("MYCODE")
#pragma data_seg("MYCODE")   // C2194
#pragma data_seg("MYCODE2")   // OK
```