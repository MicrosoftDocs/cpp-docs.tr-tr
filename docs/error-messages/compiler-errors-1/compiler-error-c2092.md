---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2092'
title: Derleyici hatası C2092
ms.date: 11/04/2016
f1_keywords:
- C2092
helpviewer_keywords:
- C2092
ms.assetid: 037e44ae-16c8-489a-a512-dcdf7f7795a6
ms.openlocfilehash: 3f89d735d44b3cc0b2c28013ab957bf433159afb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251888"
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
