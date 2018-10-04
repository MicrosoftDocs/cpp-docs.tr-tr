---
title: no_injected_text (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.no_injected_text
dev_langs:
- C++
helpviewer_keywords:
- no_injected_text attribute
ms.assetid: 5256f808-e41e-4f4a-9ea5-e447919f5696
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a9289c1b8f28b90dd5a3a4a437d3e2a5870e8468
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789985"
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
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)  