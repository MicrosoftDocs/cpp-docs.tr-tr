---
title: Derleyici hatası C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: 57c21f7ee9435220a9ca0b50bb85567506b6ad3e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207226"
---
# <a name="compiler-error-c2150"></a>Derleyici hatası C2150

> '*tanımlayıcı*': bit alanının türü ' int ', ' signed int ' veya ' unsigned int ' olmalıdır

Bit alanı için temel türün `int`, `signed int`veya `unsigned int`olması gerekir.

## <a name="example"></a>Örnek

Bu örnekte C2150 ile nasıl karşılaşacağınız ve nasıl gidereceğiniz gösterilmektedir:

```cpp
// C2150.cpp
// compile with: /c
struct A {
   float a : 8;    // C2150
   int i : 8;      // OK
};
```
