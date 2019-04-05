---
title: Derleyici Hatası C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: a3c69b05e22c2d267ad07f19a0d0ab60f3eebb94
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58779020"
---
# <a name="compiler-error-c3625"></a>Derleyici Hatası C3625

'native_type': yerel bir tür, yönetilen veya WinRT türetilemez 'type' yazın

Yönetilen veya WinRT yerel bir sınıfı devralamaz sınıfı. Daha fazla bilgi için [sınıfları ve yapıları](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3625 oluşturur:

```
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
