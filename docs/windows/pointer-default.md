---
title: pointer_default | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 54b02ab188ddd122bd3751f73a3edb33d87266f9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388218"
---
# <a name="pointerdefault"></a>pointer_default

Parametre listelerindeki görünen üst düzey işaretçileri dışındaki tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ pointer_default(
   value
) ]
```

### <a name="parameters"></a>Parametreler

*value*<br/>
İşaretçi türü tanımlayan bir değer: **ptr**, **ref**, veya **benzersiz**.

## <a name="remarks"></a>Açıklamalar

**Pointer_default** C++ özniteliği ile aynı işlevlere sahip [pointer_default](/windows/desktop/Midl/pointer-default) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [defaultvalue](../windows/defaultvalue.md) örnek kullanımı için **pointer_default**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Arabirim Öznitelikleri](../windows/interface-attributes.md)  