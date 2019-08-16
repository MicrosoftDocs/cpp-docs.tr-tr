---
title: Giriş (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 71abf4f183255fa137b43ac9cabd88d15c3fc85d
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490897"
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

**Entry** C++ özniteliği, MIDL özniteliğiyle aynı işlevselliğe sahiptir [](/windows/win32/Midl/entry) .

## <a name="example"></a>Örnek

**Girişin**örnek kullanımı için bkz. [idl_module](idl-module.md) .

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|`idl_module`özniteliğe|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)