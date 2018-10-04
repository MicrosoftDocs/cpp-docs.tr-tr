---
title: HelpString (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ea4a1ac927d03b0fc6427fb6ad39f748655fda7
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790025"
---
# <a name="helpstring"></a>helpstring

Uygulandığı öğe açıklamak için kullanılan bir karakter dizesi belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ helpstring("string") ]
```

### <a name="parameters"></a>Parametreler

*string*<br/>
Yardım dizesi metni.

## <a name="remarks"></a>Açıklamalar

**Helpstring** C++ özniteliği ile aynı işlevlere sahip [helpstring](/windows/desktop/Midl/helpstring) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [defaultvalue](defaultvalue.md) nasıl kullanılacağına ilişkin bir örnek **helpstring**.

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
[helpcontext](helpcontext.md)  