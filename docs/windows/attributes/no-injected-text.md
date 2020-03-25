---
title: no_injected_text (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 5f98be3478b2e1eeb4b464f1784f3f4ece22d8a4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166620"
---
# <a name="no_injected_text"></a>no_injected_text

Öznitelik kullanımı sonucu olarak derleyicinin ekleme kodundan yapılmasını engeller.

## <a name="syntax"></a>Sözdizimi

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Parametreler

*Boolean*<br/>
Seçim kod eklemek istiyorsanız **true** , kodun eklenmesine izin vermek için **false** . Varsayılan değer **true** 'dur.

## <a name="remarks"></a>Açıklamalar

**No_injected_text** C++ özniteliğinin en yaygın kullanımı, **no_injected_text** özniteliğini. mrg dosyasına ekleyen [/FX](../../build/reference/fx-merge-injected-code.md) derleyici seçeneğidir.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)
