---
title: HelpFile (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 7aff6addffb13d2d45953d190eeaac518fe48d6d
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039313"
---
# <a name="helpfile"></a>helpfile

Bir tür kitaplığı için Yardım dosyasına adını ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Yardım konuları içeren dosyanın adı.

## <a name="remarks"></a>Açıklamalar

**Helpfile** C++ özniteliği ile aynı işlevlere sahip [helpfile](/windows/desktop/Midl/helpfile) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [Modülü](module-cpp.md) nasıl kullanılacağına ilişkin bir örnek **helpfile**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|**arabirimi**, **typedef**, **sınıfı**, yöntemi **özelliği**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|None|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)