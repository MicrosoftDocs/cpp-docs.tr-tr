---
title: Derleyici Uyarısı C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: ae782ea0a11bd72c867ea9532a62d0b14cd98453
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684398"
---
# <a name="compiler-warning-c4986"></a>Derleyici Uyarısı C4986

' function ': özel durum belirtimi önceki bildirimle eşleşmiyor

Bu uyarı, bir bildirimde diğeri dışında bir özel durum belirtimi olduğunda oluşturulabilir.

Varsayılan olarak, C4986 kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C4986 oluşturur.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1()
{
    // ...
}
```

Aşağıdaki örnek bu uyarıyı ortadan kaldırır.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1() throw (X*)
{
    // ...
}
```
