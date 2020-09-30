---
title: Derleyici hatası C3370
ms.date: 11/04/2016
f1_keywords:
- C3370
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
ms.openlocfilehash: 4200cb7840899ad7b3719e949138010bd478ea3f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503177"
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
