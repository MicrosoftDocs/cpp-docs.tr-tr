---
title: kimlik (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.id
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
ms.openlocfilehash: 79e49b2c074cd82323c74489e33812c10c442c61
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168063"
---
# <a name="id"></a>id

Bir üye işlev için bir *DISPID* parametresi belirtir (bir özellik veya bir yöntem, bir arabirim veya dispınterface).

## <a name="syntax"></a>Sözdizimi

```cpp
[ id(dispid) ]
```

### <a name="parameters"></a>Parametreler

*dı*<br/>
Arabirim yöntemi için dağıtım KIMLIĞI.

## <a name="remarks"></a>Açıklamalar

**ID** C++ özniteliği, [ID](/windows/win32/Midl/id) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Kimliği**nasıl kullanacağınızı gösteren bir [örnek için bkz](bindable.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Interface yöntemi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Yöntem Öznitelikleri](method-attributes.md)<br/>
[Veri Üyesi Öznitelikleri](data-member-attributes.md)<br/>
[defaultvalue](defaultvalue.md)<br/>
[in](in-cpp.md)<br/>
[out](out-cpp.md)
