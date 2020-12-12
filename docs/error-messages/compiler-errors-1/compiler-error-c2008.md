---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2008'
title: Derleyici hatası C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 3fcde1885fd752a03a1285470a232f1daaa27df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298532"
---
# <a name="compiler-error-c2008"></a>Derleyici hatası C2008

' karakter ': makro tanımında beklenmiyor

Karakter, makro adının hemen sonrasında görünür. Hatayı gidermek için makro adından sonra bir boşluk olması gerekir.

Aşağıdaki örnek C2008 oluşturur:

```cpp
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

Olası çözüm:

```cpp
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```
