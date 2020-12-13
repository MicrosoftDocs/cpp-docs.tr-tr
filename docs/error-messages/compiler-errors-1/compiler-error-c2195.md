---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2195'
title: Derleyici hatası C2195
ms.date: 11/04/2016
f1_keywords:
- C2195
helpviewer_keywords:
- C2195
ms.assetid: 9f9f035c-9c51-4173-a8ea-c6f907fc5c63
ms.openlocfilehash: dbae1b48b5dc8d7c04e103dc15ca66f0183f0dbb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337626"
---
# <a name="compiler-error-c2195"></a>Derleyici hatası C2195

' tanımlayıcı ': bir veri segmenti

`code_seg`Pragma, pragma ile kullanılan bir segment adı kullanır `data_seg` .

Aşağıdaki örnek C2195 oluşturur:

```cpp
// C2195.cpp
#pragma data_seg("MYDATA")
#pragma code_seg("MYDATA")   // C2195
#pragma code_seg("MYDATA2")   // OK
```
