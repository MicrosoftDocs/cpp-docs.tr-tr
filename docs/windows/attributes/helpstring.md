---
title: HelpString (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 57f7a5bfd5bd0e7a6509797ec34e88531304ec92
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88831040"
---
# <a name="helpstring"></a>helpstring

Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>Parametreler

*dizisinde*<br/>
Yardım dizesinin metni.

## <a name="remarks"></a>Açıklamalar

**HelpString** C++ özniteliği, [HelpString](/windows/win32/Midl/helpstring) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**HelpString**'i nasıl kullanacağınızı gösteren bir örnek için bkz. [DefaultValue](defaultvalue.md) örneği.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arabirim**, **`typedef`** , **`class`** , yöntem, Özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)
