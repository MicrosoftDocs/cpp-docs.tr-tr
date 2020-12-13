---
description: 'Hakkında daha fazla bilgi edinin: HelpContext'
title: HelpContext (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: cfedec2f7650490dd266331e6853ba47265aa4ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335718"
---
# <a name="helpcontext"></a>helpcontext

Kullanıcının **Yardım** dosyasında bu öğeyle ilgili bilgileri görüntülemesine imkan tanıyan BIR bağlam kimliği belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Yardım konusunun bağlam KIMLIĞI. Bağlam kimlikleri hakkında daha fazla bilgi için bkz. [HTML Yardımı: programlarınıza yönelik yardım Context-Sensitive](../../mfc/html-help-context-sensitive-help-for-your-programs.md) .

## <a name="remarks"></a>Açıklamalar

**HelpContext** C++ özniteliği, [HelpContext](/windows/win32/Midl/helpcontext) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**HelpContext**'in nasıl kullanılacağına ilişkin bir örnek için bkz. [DefaultValue](defaultvalue.md) örneği.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arabirim**, **`typedef`** , **`class`** , yöntem, Özellik|
|**Yinelenebilir**|Hayır|
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
