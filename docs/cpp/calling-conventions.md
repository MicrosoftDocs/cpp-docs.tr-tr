---
title: Çağırma Kuralları
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
ms.openlocfilehash: cc79a0636f900aa49e31f0dc35ee19657c3e1ccb
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53626740"
---
# <a name="calling-conventions"></a>Çağırma Kuralları

Visual C/C++ derleyicisi, iç ve dış işlevleri çağırmak için birkaç farklı kural sağlar. Bu farklı yaklaşımların anlaşılması, programınızdaki hataları ayıklamanıza ve kodunuzu derleme dili yordamlarına bağlamanıza yardımcı olur.

Bu bölümdeki konular, çağırma kuralları arasındaki farkları, bağımsız değişkenlerin nasıl geçirildiğini ve değerlerin işlevler tarafından nasıl döndürüldüğünü açıklamaktadır. Bunlar, kendi giriş ve sonuç kodunuzu yazmanızı sağlayan gelişmiş bir işlev olan çıplak işlev çağrılarını da açıklamaktadır.

X64 için çağırma kuralları hakkında daha fazla bilgi için işlemciler bkz [çağırma kuralı](../build/x64-calling-convention.md).

## <a name="topics-in-this-section"></a>Bu bölümdeki konular

- [Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md) (`__cdecl`, `__stdcall`, `__fastcall`ve diğerleri)

- [Çağırma örneği: İşlev prototipi ve çağrı](../cpp/calling-example-function-prototype-and-call.md)

- [Özel giriş/Sonuç kodu yazmak için çıplak işlev çağrılarını kullanma](../cpp/naked-function-calls.md)

- [Kayan Nokta Eşişlemcisi ve Çağırma Kuralları](../cpp/floating-point-coprocessor-and-calling-conventions.md)

- [Eski çağırma kuralları](../cpp/obsolete-calling-conventions.md)

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft'a Özel Değiştiriciler](../cpp/microsoft-specific-modifiers.md)