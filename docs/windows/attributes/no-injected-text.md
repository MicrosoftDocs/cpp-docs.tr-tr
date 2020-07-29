---
title: no_injected_text (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 7e5c822c45888f41e8dd849f25658d0139e6fda0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87201251"
---
# <a name="no_injected_text"></a>no_injected_text

Öznitelik kullanımı sonucu olarak derleyicinin ekleme kodundan yapılmasını engeller.

## <a name="syntax"></a>Söz dizimi

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
(İsteğe bağlı) **`true`** kod eklemek istiyorsanız **`false`** kodun eklenmesine izin verin. **`true`** varsayılandır.

## <a name="remarks"></a>Açıklamalar

**No_injected_text** C++ özniteliğinin en yaygın kullanımı, **no_injected_text** özniteliğini. mrg dosyasına ekleyen [/FX](../../build/reference/fx-merge-injected-code.md) derleyici seçeneğidir.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)
