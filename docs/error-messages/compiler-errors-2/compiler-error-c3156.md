---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3156'
title: Derleyici hatası C3156
ms.date: 11/04/2016
f1_keywords:
- C3156
helpviewer_keywords:
- C3156
ms.assetid: 1876da78-b94e-4af7-9795-28f72b209b3e
ms.openlocfilehash: 265e887a7d075267e7a46d47d6bae9621bd83656
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174149"
---
# <a name="compiler-error-c3156"></a>Derleyici hatası C3156

' class ': yönetilen veya WinRT türünün yerel bir tanımına sahip olamaz

Bir işlev, yönetilen veya WinRT sınıfının, yapısının veya arabiriminin tanımını veya bildirimini içeremez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3156 oluşturur.

```cpp
// C3156.cpp
// compile with: /clr /c
void f() {
   ref class X {};   // C3156
   ref class Y;   // C3156
}
```
