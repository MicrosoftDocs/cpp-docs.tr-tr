---
title: HelpContext (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 22023b4087c67b62d540d021fa06fd3582c7e4e2
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038180"
---
# <a name="helpcontext"></a>helpcontext

Bu öğe ile ilgili kullanıcı bilgilerini görüntüle sağlayan bir bağlam kimliği belirtir **yardımcı** dosya.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Yardım içeriği kimliği. Bkz: [HTML Yardımı: Programlarınızı için bağlama duyarlı Yardım](../../mfc/html-help-context-sensitive-help-for-your-programs.md) bağlam kimlikleri hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

**Helpcontext** C++ özniteliği ile aynı işlevlere sahip [helpcontext](/windows/desktop/Midl/helpcontext) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [defaultvalue](defaultvalue.md) nasıl kullanılacağına ilişkin bir örnek **helpcontext**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**arabirimi**, **typedef**, **sınıfı**, yöntem, özellik|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)