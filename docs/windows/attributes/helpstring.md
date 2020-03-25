---
title: HelpString (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpstring
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
ms.openlocfilehash: d22ecf5a7131a1368abf2b1fbd8261ec6195b51e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166971"
---
# <a name="helpstring"></a>helpstring

Uygulandığı öğeyi anlatmak için kullanılan bir karakter dizesini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>Parametreler

*string*<br/>
Yardım dizesinin metni.

## <a name="remarks"></a>Açıklamalar

**HelpString** C++ özniteliği, [HelpString](/windows/win32/Midl/helpstring) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**HelpString**'i nasıl kullanacağınızı gösteren bir örnek için bkz. [DefaultValue](defaultvalue.md) örneği.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**Interface**, **typedef**, **Class**, Method, Property|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpcontext](helpcontext.md)
