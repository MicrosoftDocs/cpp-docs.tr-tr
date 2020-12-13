---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3065'
title: Derleyici hatası C3065
ms.date: 11/04/2016
f1_keywords:
- C3065
helpviewer_keywords:
- C3065
ms.assetid: e7a0bc69-1c68-459e-a7c4-93c65609ff7c
ms.openlocfilehash: 9c3c2ef0d788a193f2f2d61bf76e7672d1deda87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341158"
---
# <a name="compiler-error-c3065"></a>Derleyici hatası C3065

sınıf olmayan kapsamda Özellik bildirimine izin verilmiyor

[Özellik](../../cpp/property-cpp.md) __declspec değiştiricisi bir sınıf dışında kullanıldı.  Bir özellik yalnızca bir sınıf içinde bildirilemez.

Aşağıdaki örnek C3065 oluşturur:

```cpp
// C3065.cpp
// compile with: /c
__declspec(property(get=get_i)) int i;   // C3065

class x {
public:
   __declspec(property(get=get_i)) int i;   // OK
};
```
