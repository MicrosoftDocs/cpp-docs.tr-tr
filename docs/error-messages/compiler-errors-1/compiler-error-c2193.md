---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2193'
title: Derleyici hatası C2193
ms.date: 11/04/2016
f1_keywords:
- C2193
helpviewer_keywords:
- C2193
ms.assetid: 9813e853-d581-4f51-bb75-4e242298a844
ms.openlocfilehash: 63fc345e2898c3fe2bf222bf83ce0d703be97972
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337650"
---
# <a name="compiler-error-c2193"></a>Derleyici hatası C2193

' tanımlayıcı ': zaten bir kesimde

Bir işlev, `alloc_text` ve pragmaları kullanılarak iki farklı parçaya yerleştirildi `code_seg` .

Aşağıdaki örnek C2193 oluşturur:

```cpp
// C2193.cpp
// compile with: /c
extern "C" void MYFUNCTION();
#pragma alloc_text(MYCODE, MYFUNCTION)
#pragma code_seg("MYCODE2")
extern "C" void MYFUNCTION() {}   // C2193
extern "C" void MYFUNCTION2() {}
```
