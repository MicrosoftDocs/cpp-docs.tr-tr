---
title: Derleyici Hatası C3809 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3809
dev_langs:
- C++
helpviewer_keywords:
- C3809
ms.assetid: 37eca584-c20c-464e-8e45-a987214b7ce4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b99cda2ab1790ce63ecbd0f6c5a3dc4d916d34c9
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104224"
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