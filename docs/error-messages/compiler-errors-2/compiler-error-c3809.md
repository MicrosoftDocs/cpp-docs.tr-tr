---
title: Derleyici Hatası C3809
ms.date: 11/04/2016
f1_keywords:
- C3809
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
ms.openlocfilehash: 5ff57050980ddb770ea2fcfa4d0be4f42f5ee834
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391900"
---
# <a name="compiler-error-c3809"></a>Derleyici Hatası C3809

'class': yönetilen veya WinRT türü, bir arkadaş işlev/sınıfı/arabirimi olamaz

Yönetilen türler ve Windows çalışma zamanı türleri arkadaş izin vermez. Bu hatayı düzeltmek değil bildirmek için arkadaş içinde yönetilen ya da Windows çalışma zamanı türleri.

Aşağıdaki örnek, C3809 oluşturur:

```
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