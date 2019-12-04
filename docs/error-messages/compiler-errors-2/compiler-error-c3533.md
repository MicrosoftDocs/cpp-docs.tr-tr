---
title: Derleyici hatası C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: ce95bba417e9be3603f15376a0fd65a48f951a2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755648"
---
# <a name="compiler-error-c3533"></a>Derleyici hatası C3533

' Type ': parametre ' Auto ' içeren bir türe sahip olamaz

Varsayılan [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği etkinse, bir yöntem veya şablon parametresi `auto` anahtar sözcüğüyle bildirilemez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Parametre bildiriminden `auto` anahtar sözcüğünü kaldırın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, `auto` anahtar sözcüğüyle bir işlev parametresi bildirdiği ve **/Zc: Auto**ile derlendiği için C3533 verir.

```cpp
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, `auto` anahtar sözcüğüyle bir şablon parametresi bildirdiğinden ve **/Zc: Auto**ile derlendiği için c++ 14 modunda C3533 verir. (C++ 17 ' de bu, türü çıkarılan tek bir tür olmayan şablon parametresi olan bir sınıf şablonunun geçerli tanımıdır.)

```cpp
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Değişken Türünü Türet)](../../build/reference/zc-auto-deduce-variable-type.md)
