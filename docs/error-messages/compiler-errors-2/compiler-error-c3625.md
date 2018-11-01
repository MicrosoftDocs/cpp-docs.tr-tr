---
title: Derleyici Hatası C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: 08ad1d09cb9149811566f67a585a718340254de9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635411"
---
# <a name="compiler-error-c3625"></a>Derleyici Hatası C3625

'native_type': yerel bir tür, yönetilen veya WinRT türetilemez 'type' yazın

Yönetilen veya WinRT yerel bir sınıfı devralamaz sınıfı. Daha fazla bilgi için [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3625 oluşturur:

```
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
