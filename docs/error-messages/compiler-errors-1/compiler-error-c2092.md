---
title: Derleyici hatası C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: 8f2b83b4099308ea1d0bb127d8cea377ab65da96
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90741897"
---
# <a name="compiler-error-c2092"></a>Derleyici hatası C2092

' Array Name ' dizi öğesi türü işlev olamaz

İşlev dizilerine izin verilmez. İşlevlere işaretçiler dizisi kullanın.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2092 oluşturur:

```cpp
// C2092.cpp
typedef void (F) ();
typedef F AT[10];   // C2092
```

Olası çözüm:

```cpp
// C2092b.cpp
// compile with: /c
typedef void (F) ();
typedef F * AT[10];
```
