---
title: HelpContext (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 831ca61f82eee913efd1ab2b1420fefb011d6c1a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062840"
---
# <a name="helpcontext"></a>helpcontext

Bu öğe ile ilgili kullanıcı bilgilerini görüntüle sağlayan bir bağlam kimliği belirtir **yardımcı** dosya.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Yardım içeriği kimliği. Bkz: [HTML Help: Context-Sensitive Help for Your Programs](../../mfc/html-help-context-sensitive-help-for-your-programs.md) bağlam kimlikleri hakkında daha fazla bilgi için.

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

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)