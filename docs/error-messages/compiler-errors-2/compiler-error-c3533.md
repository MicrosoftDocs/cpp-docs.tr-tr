---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3533'
title: Derleyici hatası C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 03506c5880cce18a27f16f0e05d3b231d14c9ce6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113204"
---
# <a name="compiler-error-c3533"></a>Derleyici hatası C3533

' Type ': parametre ' Auto ' içeren bir türe sahip olamaz

**`auto`** Varsayılan [/Zc: Auto](../../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği etkinse, bir yöntem veya şablon parametresi anahtar sözcüğü ile bildirilemez.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. **`auto`** Anahtar sözcüğünü parametre bildiriminden kaldırın.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, anahtar sözcüğüyle bir işlev parametresi bildirdiği **`auto`** ve **/Zc: Auto** ile derlendiği için C3533 verir.

```cpp
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

Aşağıdaki örnek, anahtar sözcükle bir şablon parametresi bildirdiğinden **`auto`** ve **/Zc: Auto** ile derlendiği için C++ 14 modunda C3533 verir. (C++ 17 ' de bu, türü çıkarılan tek bir tür olmayan şablon parametresi olan bir sınıf şablonunun geçerli tanımıdır.)

```cpp
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-cpp.md)<br/>
[/Zc: Auto (değişken türünü türet)](../../build/reference/zc-auto-deduce-variable-type.md)
