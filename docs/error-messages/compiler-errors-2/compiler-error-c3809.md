---
title: Derleyici hatası C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 889d9a108ab0dfb0101fb9ec9c367db9378b1128
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757143"
---
# <a name="compiler-error-c3809"></a>Derleyici hatası C3809

' class ': yönetilen veya WinRT türünün hiçbir arkadaş işlevi/sınıfı/arabirimi olamaz

Yönetilen türler ve Windows Çalışma Zamanı türleri arkadaşlara izin vermez. Bu hatayı onarmak için, arkadaşları yönetilen veya Windows Çalışma Zamanı türleri içinde bildirmeyin.

Aşağıdaki örnek C3809 oluşturur:

```cpp
// C3809a.cpp
// compile with: /clr
ref class A {};

ref class B
{
public:
   friend ref class A;   // C3809
};

int main()
{
}
```
