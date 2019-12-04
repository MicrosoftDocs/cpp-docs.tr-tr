---
title: Derleyici hatası C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: b530663cae2292ebeab1b871e495e9a45e4633cf
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754673"
---
# <a name="compiler-error-c2092"></a>Derleyici hatası C2092

' Array Name ' dizi öğesi türü işlev olamaz

İşlev dizilerine izin verilmez. İşlevlere işaretçiler dizisi kullanın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2092 oluşturur:

```cpp
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

## <a name="example"></a>Örnek

Olası çözüm:

```cpp
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```
