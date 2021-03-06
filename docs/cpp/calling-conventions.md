---
description: 'Daha fazla bilgi edinin: çağırma kuralları'
title: Çağırma Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: bb5dab14e9d046b6ccee75a4fb37bd7b105902dc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97308659"
---
# <a name="calling-conventions"></a>Çağırma Kuralları

Visual C/C++ derleyicisi, iç ve dış işlevleri çağırmak için birkaç farklı kural sağlar. Bu farklı yaklaşımların anlaşılması, programınızdaki hataları ayıklamanıza ve kodunuzu derleme dili yordamlarına bağlamanıza yardımcı olur.

Bu bölümdeki konular, çağırma kuralları arasındaki farkları, bağımsız değişkenlerin nasıl geçirildiğini ve değerlerin işlevler tarafından nasıl döndürüldüğünü açıklamaktadır. Bunlar, kendi giriş ve sonuç kodunuzu yazmanızı sağlayan gelişmiş bir işlev olan çıplak işlev çağrılarını da açıklamaktadır.

X64 işlemcilerin kuralları çağırma hakkında daha fazla bilgi için bkz. [çağırma kuralı](../build/x64-calling-convention.md).

## <a name="topics-in-this-section"></a>Bu bölümdeki konular

- [Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md) ( **`__cdecl`** ,, **`__stdcall`** **`__fastcall`** ve diğerleri)

- [Çağırma örneği: Işlev prototipi ve çağrı](../cpp/calling-example-function-prototype-and-call.md)

- [Özel giriş/bitiş kodu yazmak için çıplak işlev çağrılarını kullanma](../cpp/naked-function-calls.md)

- [Kayan nokta Coprocessor ve çağırma kuralları](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [Kullanılmayan çağırma kuralları](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft 'a özgü değiştiriciler](../cpp/microsoft-specific-modifiers.md)
