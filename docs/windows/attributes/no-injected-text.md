---
title: no_injected_text (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: ab718376d5da7214813d5ab2e0caaa7bbccd077b
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88844086"
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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)
