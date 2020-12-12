---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3279'
title: Derleyici hatası C3279
ms.date: 11/04/2016
f1_keywords:
- C3279
helpviewer_keywords:
- C3279
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
ms.openlocfilehash: c257a97cad1603703e7dbf2ed0d9f5cb3e6134a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258024"
---
# <a name="compiler-error-c3279"></a>Derleyici hatası C3279

hem kısmi hem de açık uzmanlık ve CLI ad alanında belirtilen sınıf şablonlarının açık örneklemeleri izin verilmiyor

`cli`Ad alanı Microsoft tarafından tanımlanır ve sözde şablonlar içerir. Microsoft C++ derleyicisi, Kullanıcı tanımlı, kısmi ve açık uzmanlık ve bu ad alanındaki sınıf şablonlarının açık örneklemeleri için izin vermez.

Aşağıdaki örnek C3279 oluşturur:

```cpp
// C3279.cpp
// compile with: /clr
namespace cli {
   template <> ref class array<int> {};   // C3279
   template <typename T> ref class array<T, 2> {};   // C3279
}
```
