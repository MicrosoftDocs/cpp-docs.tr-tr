---
title: HelpContext (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 60e6bf66e088872a357751e4a7b7e043cd9b4dfc
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845256"
---
# <a name="helpcontext"></a>helpcontext

Kullanıcının **Yardım** dosyasında bu öğeyle ilgili bilgileri görüntülemesine imkan tanıyan BIR bağlam kimliği belirtir.

## <a name="syntax"></a>Söz dizimi

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
[helpstring](helpstring.md)
