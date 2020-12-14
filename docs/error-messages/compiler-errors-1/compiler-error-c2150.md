---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2150'
title: Derleyici hatası C2150
ms.date: 11/04/2016
f1_keywords:
- C2150
helpviewer_keywords:
- C2150
ms.assetid: 21e82a10-c1d4-4c0d-9dc6-c5d92ea42a31
ms.openlocfilehash: 5a609edba74e2aee8e0d2a6275fa1ca40fafe5c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223522"
---
# <a name="compiler-error-c2150"></a>Derleyici hatası C2150

> '*tanımlayıcı*': bit alanının türü ' int ', ' signed int ' veya ' unsigned int ' olmalıdır

Bit alanı için temel türün **`int`** , **`signed int`** , veya olması gerekir **`unsigned int`** .

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
