---
title: Derleyici Hatası C3371
ms.date: 11/04/2016
f1_keywords:
- C3371
helpviewer_keywords:
- C3371
ms.assetid: f7ecf1aa-ed0a-4f73-81e5-62cf98f88ea1
ms.openlocfilehash: 7967f6fa92434dcac35ec732f42a32531bfcce03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565314"
---
# <a name="compiler-error-c3371"></a>Derleyici Hatası C3371

'idl_module': Burada yalnızca 'name' özelliğine izin

[idl_module](../../windows/idl-module.md) kullanımı doğrudan bir işlev bildirimi, adı dışında herhangi bir parametre olamaz.

Aşağıdaki örnek, C3371 oluşturur:

```
// C3371.cpp
[idl_module(name="Name", dllname="Some.dll")];
[idl_module(name="Name", helpstring="Some help")]   // C3371
int f1();
// try
// [idl_module(name="Name")]
// int f1();

int main()
{
}
```