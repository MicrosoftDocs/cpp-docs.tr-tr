---
title: Derleyici hatası C2195
ms.date: 11/04/2016
f1_keywords:
- C2195
helpviewer_keywords:
- C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
ms.openlocfilehash: 748516dbcdf5e135964e720d6215f31091bfed9e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758534"
---
# <a name="compiler-error-c2195"></a>Derleyici hatası C2195

' tanımlayıcı ': bir veri segmenti

`code_seg` pragma `data_seg` pragma ile kullanılan bir segment adı kullanır.

Aşağıdaki örnek C2195 oluşturur:

```cpp
// C2195.cpp
#pragma data_seg("MYDATA")
#pragma code_seg("MYDATA")   // C2195
#pragma code_seg("MYDATA2")   // OK
```
