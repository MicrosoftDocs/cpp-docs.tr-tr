---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3809'
title: Derleyici hatası C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 62e7ff06e6ed5bf34861fdbae3f823e19ad5aad4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97328200"
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
