---
title: Derleyici Hatası C3747
ms.date: 11/04/2016
f1_keywords:
- C3747
helpviewer_keywords:
- C3747
ms.assetid: a9a4be67-5d9c-4dcc-9ae9-baae46cbecde
ms.openlocfilehash: 860a990e35b0d51dfc1316a11a2d2512eb40c273
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62226802"
---
# <a name="compiler-error-c3747"></a>Derleyici Hatası C3747

varsayılan tür parametresi eksik: parametre param

Varsayılan değeri olan parametrelere genel veya şablon parametre listesinde varsayılan değerlere sahip olmayan parametreler tarafından izlenemiyor.

Aşağıdaki örnek, C3747 oluşturur:

```
// C3747.cpp
template <class T1 = int, class T2>   // C3747
struct MyStruct {};
```

Olası çözüm:

```
// C3747b.cpp
// compile with: /c
template <class T1, class T2 = int>
struct MyStruct {};
```