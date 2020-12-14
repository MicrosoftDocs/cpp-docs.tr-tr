---
description: 'Daha fazla bilgi edinin: giriş'
title: Giriş (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: fbceea4c23d730ceba780ce68398a9d78fa9c33b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259233"
---
# <a name="entry"></a>giriş

DLL 'deki giriş noktasını tanımlayarak bir modülde, bir içe aktarılmış işlevi veya sabiti belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Giriş noktasının KIMLIĞI.

## <a name="remarks"></a>Açıklamalar

**Giriş** C++ özniteliği, [giriş](/windows/win32/Midl/entry) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Girişin** örnek kullanımı için [idl_module](idl-module.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|`idl_module` özniteliği|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)
