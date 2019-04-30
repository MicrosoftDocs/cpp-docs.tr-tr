---
title: Derleyici Hatası C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: 0cd27da4b73732513afe0bd33a2d7312e6ddbe97
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388741"
---
# <a name="compiler-error-c3369"></a>Derleyici Hatası C3369

'modül adı': idl_module zaten tanımlanmış

[İdl_module](../../windows/idl-module.md) DLL tanımladığınız kullanım yalnızca oluşabilir kez bir programda.

Aşağıdaki örnek, C3369 oluşturur:

```
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```