---
title: auto Anahtar Sözcüğü
ms.date: 05/07/2019
ms.assetid: 744a41c0-2510-4140-a1be-96257e722908
ms.openlocfilehash: a695c33ab55601bb8d81b00f963646f6a48f09d5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222252"
---
# <a name="auto-keyword"></a>auto Anahtar Sözcüğü

**Otomatik** anahtar sözcüğü, bir bildirim belirticisidir. Ancak, C++ standardı bu anahtar sözcük için özgün ve düzeltilmiş bir anlamı tanımlar. Visual Studio 2010 önce **otomatik** anahtar sözcüğü bir değişken bildirir *otomatik* depolama sınıfı; diğer bir deyişle, yerel kullanım ömrüne sahip bir değişken. Visual Studio 2010 ile başlayarak **otomatik** anahtar sözcüğü, türü atanan bildiriminden başlatma ifadesinden bir değişken bildirir. [/Zc:auto&#91;-&#93; ](../build/reference/zc-auto-deduce-variable-type.md) derleyici seçeneği anlamını denetler **otomatik** anahtar sözcüğü.

## <a name="syntax"></a>Sözdizimi

```cpp
auto declarator ;
auto declarator initializer;
```

## <a name="remarks"></a>Açıklamalar

Tanımı **otomatik** anahtar sözcüğü değişiklikleri C++ programlama dilinde, ancak C programlama dilini içinde değil.

Aşağıdaki konularda açıklanmıştır **otomatik** anahtar sözcüğü ve karşılık gelen derleyici seçeneği:

- [Otomatik](../cpp/auto-cpp.md) yeni tanımını açıklar **otomatik** anahtar sözcüğü.

- [/ZC:Auto (değişken türünü türet)](../build/reference/zc-auto-deduce-variable-type.md) hangi tanımının derleyiciye bildiren derleyici seçeneğini açıklar **otomatik** anahtar sözcüğünü kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)