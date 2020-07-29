---
title: HelpFile (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 641823779346bf5417ec0db26b83083fa949e960
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222127"
---
# <a name="helpfile"></a>helpfile

Bir tür kitaplığı için yardım dosyasının adını ayarlar.

## <a name="syntax"></a>Söz dizimi

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Yardım konularını içeren dosyanın adı.

## <a name="remarks"></a>Açıklamalar

**HelpFile** C++ özniteliği, [HelpFile](/windows/win32/Midl/helpfile) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**HelpFile**öğesinin nasıl kullanılacağına ilişkin bir örnek için [Modül](module-cpp.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Şunlara uygulanır**|**arabirim**, **`typedef`** , **`class`** , yöntem,**`property`**|
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
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)
