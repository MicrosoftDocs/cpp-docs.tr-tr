---
title: propputref (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: dbb5d5966fc82f69be0ed7d2fa0a66ad558a7915
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839913"
---
# <a name="propputref"></a>propputref

Değer yerine başvuru kullanan bir özellik ayarı işlevi belirtir.

## <a name="syntax"></a>Syntax

```cpp
[propputref]
```

## <a name="remarks"></a>Açıklamalar

**Propputref** C++ özniteliği, [propputref](/windows/win32/Midl/propputref) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Propputref**'in örnek kullanımı için [bağlanabilir](bindable.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Yöntem|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|`propget`, `propput`|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)
