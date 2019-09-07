---
title: Derleyici hatası C2234
ms.date: 11/04/2016
f1_keywords:
- C2234
helpviewer_keywords:
- C2234
ms.assetid: cfa42458-c803-4717-a017-9eca1c0cbfb0
ms.openlocfilehash: 16cc09f43f8705452c207e5218f4cc274557e825
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741142"
---
# <a name="compiler-error-c2234"></a>Derleyici hatası C2234

' name ': başvuru dizileri geçersizdir

Başvurulara yönelik işaretçilere izin verilmediğinden, başvuru dizileri mümkün değildir.

Aşağıdaki örnek C2234 oluşturur:

```
// C2234.cpp
int main() {
   int i = 0, j = 0, k = 0, l = 0;
   int &array[4] = {i,j,k,l};   // C2234
   int array2[4] = {i,j,k,l};   // OK
}
```