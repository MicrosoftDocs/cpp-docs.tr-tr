---
title: pointer_default (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pointer_default
dev_langs:
- C++
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6e8ddf566082bfded1f20a2bfe04e7cef0b5dc14
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789575"
---
# <a name="pointerdefault"></a>pointer_default

Parametre listelerindeki görünen üst düzey işaretçileri dışındaki tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Parametreler

*value*<br/>
İşaretçi türü tanımlayan bir değer: **ptr**, **ref**, veya **benzersiz**.

## <a name="remarks"></a>Açıklamalar

**Pointer_default** C++ özniteliği ile aynı işlevlere sahip [pointer_default](/windows/desktop/Midl/pointer-default) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [defaultvalue](defaultvalue.md) örnek kullanımı için **pointer_default**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)  