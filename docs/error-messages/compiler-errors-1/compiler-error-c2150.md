---
title: Derleyici Hatası C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: a9c6465ef87c12135ad4e6709741f0027d8ea3c7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175153"
---
# <a name="compiler-error-c2150"></a>Derleyici Hatası C2150

> '*tanımlayıcı*': bit alanının türü 'int', 'signed int' veya 'unsigned int' olmalıdır

Bir bit alanına yönelik temel türü olmasını gerekli `int`, `signed int`, veya `unsigned int`.

## <a name="example"></a>Örnek

Bu örnek nasıl C2150 karşılaşabileceğiniz ve nasıl düzeltebilirsiniz gösterir:

```cpp
// C2150.cpp
// compile with: /c
struct A {
   float a : 8;    // C2150
   int i : 8;      // OK
};
```