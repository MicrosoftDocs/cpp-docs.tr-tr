---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3625'
title: Derleyici hatası C3625
ms.date: 11/04/2016
f1_keywords:
- C3625
helpviewer_keywords:
- C3625
ms.assetid: fdf49f21-d6b1-42f4-9eec-23b04ae8b4aa
ms.openlocfilehash: ee28175eac35e05ca2a4620dffa84cf995e053a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144501"
---
# <a name="compiler-error-c3625"></a>Derleyici hatası C3625

' native_type ': yerel bir tür yönetilen veya WinRT türünden ' Type ' öğesinden türetilemez

Yerel bir sınıf yönetilen veya WinRT sınıfından devralınabilir. Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3625 oluşturur:

```cpp
// C3625.cpp
// compile with: /clr /c
ref class B {};
class D : public B {};   // C3625 cannot inherit from a managed class
```
