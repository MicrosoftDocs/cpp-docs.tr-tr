---
title: Derleyici Hatası C3370
ms.date: 11/04/2016
f1_keywords:
- C3370
helpviewer_keywords:
- C3370
ms.assetid: ee6d4c85-78fc-42b2-836e-5cc491a3b2ba
ms.openlocfilehash: 0dbc95fcb26354b0f963d1844ddd6a43783c532a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466176"
---
# <a name="compiler-error-c3370"></a>Derleyici Hatası C3370

'idl_module name': idl_module henüz tanımlanmadı

Kullanmadan önce [idl_module](../../windows/idl-module.md) DLL'de bir giriş noktası belirtmek için önce kullanmalısınız `idl_module` DLL adını belirtmek için.

Aşağıdaki örnek, C3370 oluşturur:

```
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