---
title: Giriş (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 63e5ccebb1d3844af8dd11b4b094abe96e3e257c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845321"
---
# <a name="entry"></a>giriş

DLL 'deki giriş noktasını tanımlayarak bir modülde, bir içe aktarılmış işlevi veya sabiti belirtir.

## <a name="syntax"></a>Söz dizimi

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Giriş noktasının KIMLIĞI.

## <a name="remarks"></a>Açıklamalar

**Giriş** C++ özniteliği, [giriş](/windows/win32/Midl/entry) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Girişin**örnek kullanımı için [idl_module](idl-module.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|`idl_module` özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)
