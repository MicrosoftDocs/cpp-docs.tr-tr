---
title: Derleyici hatası C3386
ms.date: 11/04/2016
f1_keywords:
- C3386
helpviewer_keywords:
- C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
ms.openlocfilehash: efe882db447b9ebc69d02e3b10d9e484a3cfd8a8
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520454"
---
# <a name="compiler-error-c3386"></a>Derleyici hatası C3386

> '*tür-adı*': `__declspec(dllexport)` / `__declspec(dllimport)` yönetilen veya WinRT türüne uygulanamaz

[`dllimport`](../../cpp/dllexport-dllimport.md)Ve [`dllexport`](../../cpp/dllexport-dllimport.md) **`__declspec`** değiştiricileri yönetilen veya Windows çalışma zamanı türünde geçerli değildir.

Aşağıdaki örnek C3386 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C3386.cpp
// compile with: /clr /c
ref class __declspec(dllimport) X1 {   // C3386
// try the following line instead
// ref class X1 {
};
```
