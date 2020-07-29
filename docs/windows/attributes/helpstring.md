---
title: HelpString (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: 18a8dbea2387224070903aa10c812c9dd079bf96
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217265"
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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|**arabirim**, **`typedef`** , **`class`** , yöntem, Özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[Yöntem öznitelikleri](method-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)
