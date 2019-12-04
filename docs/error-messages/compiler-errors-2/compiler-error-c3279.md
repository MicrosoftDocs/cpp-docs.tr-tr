---
title: Derleyici hatası C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: 3025dbf7c6bf4701218c2d9a956cae26d7180848
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757611"
---
# <a name="compiler-error-c3279"></a>Derleyici hatası C3279

hem kısmi hem de açık uzmanlık ve CLI ad alanında belirtilen sınıf şablonlarının açık örneklemeleri izin verilmiyor

`cli` ad alanı Microsoft tarafından tanımlanır ve sözde şablonlar içerir. Microsoft C++ derleyicisi, Kullanıcı tanımlı, kısmi ve açık uzmanlık ve bu ad alanındaki sınıf şablonlarının açık örneklemeleri için izin vermez.

Aşağıdaki örnek C3279 oluşturur:

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
