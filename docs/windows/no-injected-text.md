---
title: no_injected_text | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: e63b0b47dcc3f53ecd5af2d51505df844f66437a
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599392"
---
# <a name="noinjectedtext"></a>no_injected_text

Derleyici, özellik kullanımı sonucu olarak kod ekleme öğesinden engeller.

## <a name="syntax"></a>Sözdizimi

```cpp
[ no_injected_text(
   boolean
) ];
```

### <a name="parameters"></a>Parametreler

*Boole* (isteğe bağlı)  
**doğru** eklenen, herhangi bir kod isterseniz **false** eklenmesi için kod izin vermek için. **doğru** varsayılandır.

## <a name="remarks"></a>Açıklamalar

En yaygın kullanımı **no_injected_text** C++ özniteliktir [/Fx](../build/reference/fx-merge-injected-code.md) ekleyen derleyici seçeneği **no_injected_text** .mrg dosyasına özniteliği.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](../windows/compiler-attributes.md)  