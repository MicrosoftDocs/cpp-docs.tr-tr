---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3370'
title: Derleyici hatası C3370
ms.date: 11/04/2016
f1_keywords:
- C3370
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
ms.openlocfilehash: 9c34636f91035177e7408dfd4b3bdaaed0fe84c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245271"
---
# <a name="compiler-error-c3370"></a>Derleyici hatası C3370

' idl_module Name ': idl_module henüz tanımlanmadı

DLL 'de bir giriş noktası belirtmek için [idl_module](../../windows/attributes/idl-module.md) kullanabilmeniz IÇIN önce `idl_module` DLL adını belirtmek üzere kullanmanız gerekir.

Aşağıdaki örnek C3370 oluşturur:

```cpp
// C3370.cpp
[module(name=MyLibrary)];
// uncomment the following line to resolve the error
// [idl_module(name="name1", dllname=x.dll)];
[idl_module(name="name1"), entry(100)] // C3370
int f1();

int main()
{
}
```
