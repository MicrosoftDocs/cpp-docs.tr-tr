---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3369'
title: Derleyici hatası C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: 0391dbd7fe80daf93c8070253181c40fb805fa82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150806"
---
# <a name="compiler-error-c3369"></a>Derleyici hatası C3369

' modül adı ': idl_module zaten tanımlandı

DLL 'yi tanımladığınız [idl_module](../../windows/attributes/idl-module.md) kullanımı, bir programda yalnızca bir kez bulunabilir.

Aşağıdaki örnek C3369 oluşturur:

```cpp
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```
