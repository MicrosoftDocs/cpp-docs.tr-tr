---
title: pointer_default (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.pointer_default
helpviewer_keywords:
- pointer_default attribute
ms.assetid: 2d0c7bbc-a1e8-4337-9e54-e304523e2735
ms.openlocfilehash: d0c5832623c1e418f4c6e8bdb606d1d363503483
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166542"
---
# <a name="pointer_default"></a>pointer_default

Parametre listelerinde görünen en üst düzey işaretçiler hariç olmak üzere tüm işaretçiler için varsayılan işaretçi özniteliğini belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ pointer_default(value) ]
```

### <a name="parameters"></a>Parametreler

*value*<br/>
İşaretçi türünü tanımlayan bir değer: **PTR**, **ref**veya **Unique**.

## <a name="remarks"></a>Açıklamalar

**Pointer_default** C++ özniteliği [pointer_default](/windows/win32/Midl/pointer-default) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Pointer_default**örnek bir kullanımı için [DefaultValue](defaultvalue.md) örneğine bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Arabirim Öznitelikleri](interface-attributes.md)
