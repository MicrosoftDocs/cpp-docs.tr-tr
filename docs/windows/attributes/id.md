---
title: Kimliği (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7ae22069acfa13bcaa71630f919b4ab3fede86a4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057692"
---
# <a name="id"></a>kimlik

Belirtir bir *DISPID* (bir özellik veya bir arabirim veya dispinterface bir yöntem), bir üye işlev için parametre.

## <a name="syntax"></a>Sözdizimi

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Parametreler

*DISPID*<br/>
Arabirim yöntemi için gönderme kimliği.

## <a name="remarks"></a>Açıklamalar

**Kimliği** C++ özniteliği ile aynı işlevlere sahip [kimliği](/windows/desktop/Midl/id) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [bağlanabilir](bindable.md) nasıl kullanılacağına ilişkin bir örnek **kimliği**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Arabirim yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Veri Üyesi Öznitelikleri](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)