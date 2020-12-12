---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3269'
title: Derleyici hatası C3269
ms.date: 11/04/2016
f1_keywords:
- C3269
helpviewer_keywords:
- C3269
ms.assetid: c575f067-244d-4dd5-bf58-9e7630ea58b7
ms.openlocfilehash: 041a0af061e4ddd1a691c396cdd15e86085124c2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113707"
---
# <a name="compiler-error-c3269"></a>Derleyici hatası C3269

' function ': yönetilen veya Wınrttype 'ın üye işlevi '... ' ile bildirilemez

Yönetilen ve WinRT sınıfı üye işlevleri, değişken uzunluklu parametre listelerini bildiremez.

Aşağıdaki örnek C3269 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3269_2.cpp
// compile with: /clr

ref struct A
{
   void func(int i, ...)   // C3269
   // try the following line instead
   // void func(int i )
   {
   }
};

int main()
{
}
```
