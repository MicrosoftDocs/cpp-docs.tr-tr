---
title: pointer_default (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: e4e5ce03e8c0e6ca19814f5d228305b0d97322f9
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836198"
---
# <a name="pointer_default"></a>pointer_default

Parametre listelerinde görünen en üst düzey işaretçiler hariç olmak üzere tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Parametreler

*deeri*<br/>
İşaretçi türünü tanımlayan bir değer: **PTR**, **ref**veya **Unique**.

## <a name="remarks"></a>Açıklamalar

**Pointer_default** C++ özniteliği, [pointer_default](/windows/win32/Midl/pointer-default) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Pointer_default**örnek bir kullanımı için [DefaultValue](defaultvalue.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**arayüz**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim öznitelikleri](interface-attributes.md)
