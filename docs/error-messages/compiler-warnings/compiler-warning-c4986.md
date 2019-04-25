---
title: Derleyici Uyarısı C4986
ms.date: 11/04/2016
f1_keywords:
- C4986
helpviewer_keywords:
- C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
ms.openlocfilehash: fb52e33ceeadda03105e391d8e0b5b3f6234d6b9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280600"
---
# <a name="compiler-warning-c4986"></a>Derleyici Uyarısı C4986

'function': özel durum belirtimi, önceki bildirimle eşleşmiyor

Bir özel durum belirtimi bir bildirim ve diğer olduğunda bu uyarı oluşturulabilir.

Varsayılan olarak, C4986 kapalıdır. Daha fazla bilgi için [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4986 oluşturur.

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

Aşağıdaki örnek, bu uyarıyı ortadan kaldırır.

```cpp
class X { };
void f1() throw (X*);
// ...
void f1() throw (X*)
{
    // ...
}
```