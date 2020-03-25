---
title: HelpContext (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 292db21e8092284a92b09ef3f889bb0475d0d886
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167010"
---
# <a name="helpcontext"></a>helpcontext

Kullanıcının **Yardım** dosyasında bu öğeyle ilgili bilgileri görüntülemesine imkan tanıyan BIR bağlam kimliği belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Yardım konusunun bağlam KIMLIĞI. Bağlam kimlikleri hakkında daha fazla bilgi için bkz. [HTML Yardımı: programlarınıza yönelik Içeriğe duyarlı yardım](../../mfc/html-help-context-sensitive-help-for-your-programs.md) .

## <a name="remarks"></a>Açıklamalar

**HelpContext** C++ özniteliği, [HelpContext](/windows/win32/Midl/helpcontext) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**HelpContext**'in nasıl kullanılacağına ilişkin bir örnek için bkz. [DefaultValue](defaultvalue.md) örneği.

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
[helpstring](helpstring.md)
