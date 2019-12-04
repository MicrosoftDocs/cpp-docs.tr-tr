---
title: Derleyici hatası C2824
ms.date: 11/04/2016
f1_keywords:
- C2824
helpviewer_keywords:
- C2824
ms.assetid: 5bd865f7-e0af-404e-80fe-e2b798b44a59
ms.openlocfilehash: ee012d7244079fd881210eb969f4844a2c6e85d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750643"
---
# <a name="compiler-error-c2824"></a>Derleyici hatası C2824

' operator New ' için dönüş türü ' void * ' olmalıdır

Tabanlı olmayan işaretçilerle, işleç `new` aşırı yüklemeleri `void *`döndürmelidir.

Aşağıdaki örnek C2824 oluşturur:

```cpp
// C2824.cpp
// compile with: /c
class   A {
   A* operator new(size_t i, char *m);   // C2824
   // try the following line instead
   // void* operator new(size_t i, char *m);
};
```
