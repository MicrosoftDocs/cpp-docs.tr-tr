---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3121'
title: Derleyici hatası C3121
ms.date: 11/04/2016
f1_keywords:
- C3121
helpviewer_keywords:
- C3121
ms.assetid: 1d3c7be4-d42d-4def-8d53-182c0c5cc237
ms.openlocfilehash: 62f12d17d8696e500cc21084645533825e7f25f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151066"
---
# <a name="compiler-error-c3121"></a>Derleyici hatası C3121

' class_name ' sınıfının GUID 'SI değiştirilemiyor

Sınıf KIMLIĞINI [__declspec (UUID)](../../cpp/uuid-cpp.md)ile değiştirmeye çalıştınız.

Örneğin, aşağıdaki kod C3121 oluşturur:

```cpp
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
