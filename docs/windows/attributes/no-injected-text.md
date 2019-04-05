---
title: no_injected_text (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.no_injected_text
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
ms.openlocfilehash: 354643020e704a87daa2e56e923b6a0a704bf0b5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59038375"
---
# <a name="noinjectedtext"></a>no_injected_text

Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.

## <a name="syntax"></a>Sözdizimi

```cpp
[ no_injected_text(boolean) ];
```

### <a name="parameters"></a>Parametreler

*Boole değeri*<br/>
(İsteğe bağlı) **true** eklenen, herhangi bir kod isterseniz **false** eklenmesi için kod izin vermek için. **doğru** varsayılandır.

## <a name="remarks"></a>Açıklamalar

En yaygın kullanımı **no_injected_text** C++ özniteliktir [/Fx](../../build/reference/fx-merge-injected-code.md) ekleyen derleyici seçeneği **no_injected_text** .mrg dosyasına özniteliği.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)