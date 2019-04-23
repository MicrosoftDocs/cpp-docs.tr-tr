---
title: propputref (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.propputref
helpviewer_keywords:
- propputref attribute
ms.assetid: 9b0aed74-fdc7-4e59-9117-949bea4f86dd
ms.openlocfilehash: e471e467c55e0b8a17be96fd1bcb3cd24cfafe06
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59031835"
---
# <a name="propputref"></a>propputref

Bir değer yerine başvurur bir özellik ayarı işlevi belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[propputref]
```

## <a name="remarks"></a>Açıklamalar

**Propputref** C++ özniteliği ile aynı işlevlere sahip [propputref](/windows/desktop/Midl/propputref) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](bindable.md) örnek kullanımı için **propputref**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Yöntem|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|`propget`, `propput`|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[propget](propget.md)<br/>
[propput](propput.md)