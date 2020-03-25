---
title: Derleyici Uyarısı C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: df6fc88ffe98dd2b4a3129800c7881f26d4f625b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164826"
---
# <a name="compiler-warning-c4986"></a>Derleyici Uyarısı C4986

' function ': özel durum belirtimi önceki bildirimle eşleşmiyor

Bu uyarı, bir bildirimde diğeri dışında bir özel durum belirtimi olduğunda oluşturulabilir.

Varsayılan olarak, C4986 kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

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

## <a name="example"></a>Örnek

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
