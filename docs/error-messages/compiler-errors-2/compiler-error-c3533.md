---
title: Derleyici Hatası C3533
ms.date: 11/04/2016
f1_keywords:
- C3533
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
ms.openlocfilehash: 7a567e4396999f98d9e9740db0acf951c443d525
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397386"
---
# <a name="compiler-error-c3533"></a>Derleyici Hatası C3533

'type': bir parametre 'auto' içeren bir tür olamaz

Bir yöntem veya şablon parametresi ile bildirilemez `auto` anahtar sözcüğü, varsayılan [/Zc:auto](../../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği etkindir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Kaldırma `auto` parametre bildirimi from anahtar sözcüğü.

## <a name="example"></a>Örnek

Aşağıdaki örnek bir işlev parametresi ile bildirdiğinden C3533 ortaya çıkarır `auto` ve anahtar sözcüğü ile derlendiğinde **/Zc:auto**.

```
// C3533a.cpp
// Compile with /Zc:auto
void f(auto j) {} // C3533
```

## <a name="example"></a>Örnek

Aşağıdaki örnek bir şablon parametresi ile bildirdiğinden C3533 C ++ 14 modu verir. `auto` ve anahtar sözcüğü ile derlendiğinde **/Zc:auto**. (C ++ 17'de, türü çıkarılır tek tür olmayan şablon parametresi ile bir sınıf şablonunun geçerli bir tanımı budur.)

```
// C3533b.cpp
// Compile with /Zc:auto
template<auto T> class C {}; // C3533
```

## <a name="see-also"></a>Ayrıca bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Değişken Türünü Türet)](../../build/reference/zc-auto-deduce-variable-type.md)
