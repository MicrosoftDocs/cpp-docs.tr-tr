---
title: HelpFile (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 7aff6addffb13d2d45953d190eeaac518fe48d6d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409570"
---
# <a name="helpfile"></a>helpfile

Bir tür kitaplığı için Yardım dosyasına adını ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Yardım konuları içeren dosyanın adı.

## <a name="remarks"></a>Açıklamalar

**Helpfile** C++ özniteliği ile aynı işlevlere sahip [helpfile](/windows/desktop/Midl/helpfile) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [Modülü](module-cpp.md) nasıl kullanılacağına ilişkin bir örnek **helpfile**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**arabirimi**, **typedef**, **sınıfı**, yöntemi **özelliği**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)