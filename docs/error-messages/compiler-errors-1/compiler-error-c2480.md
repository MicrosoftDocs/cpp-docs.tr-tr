---
title: Derleyici hatası C2480
ms.date: 11/04/2016
f1_keywords:
- C2480
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
ms.openlocfilehash: 3e495a8019405a558511637467133877dae1183e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74743529"
---
# <a name="compiler-error-c2480"></a>Derleyici hatası C2480

' tanımlayıcı ': ' Thread ' yalnızca statik kapsamın veri öğeleri için geçerlidir

`thread` özniteliğini bir otomatik değişken, statik olmayan veri üyesi, işlev parametresi veya işlev bildirimleri veya tanımlarında kullanamazsınız.

Genel değişkenler, statik veri üyeleri ve yalnızca yerel statik değişkenler için `thread` özniteliğini kullanın.

Aşağıdaki örnek C2480 oluşturur:

```cpp
// C2480.cpp
// compile with: /c
__declspec( thread ) void func();   // C2480
__declspec( thread ) static int i;   // OK
```
