---
title: Derleyici Hatası C3533 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3533
dev_langs:
- C++
helpviewer_keywords:
- C3533
ms.assetid: a68b1ba5-466e-4190-a1a4-505ccfe548b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6201f59e3ccefaa920f79f9b9889bd187fb2e0b0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042565"
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

## <a name="see-also"></a>Ayrıca Bkz.

[auto Anahtar Sözcüğü](../../cpp/auto-keyword.md)<br/>
[/Zc:auto (Değişken Türünü Türet)](../../build/reference/zc-auto-deduce-variable-type.md)
