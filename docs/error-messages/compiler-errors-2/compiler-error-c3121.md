---
title: Derleyici Hatası C3121
ms.date: 11/04/2016
f1_keywords:
- C3121
helpviewer_keywords:
- C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
ms.openlocfilehash: cd8f23a3edbdee4dc4edc294494cb9d73cf6b998
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300719"
---
# <a name="compiler-error-c3121"></a>Derleyici Hatası C3121

GUID '$class_name' sınıfı için değiştiremezsiniz.

Sınıf kimliği ile değiştirmeye çalıştığınız [__declspec(uuid)](../../cpp/uuid-cpp.md).

Örneğin, aşağıdaki kod C3121 oluşturur:

```
// C3121.cpp
[emitidl];
[module(name="MyLibrary")];

[coclass, uuid="00000000-0000-0000-0000-111111111111"]
class __declspec(uuid("00000000-0000-0000-0000-111111111112")) A   // C3121
{
};
int main()
{
}
```