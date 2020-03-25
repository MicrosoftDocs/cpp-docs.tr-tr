---
title: Giriş (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 9bdfc64506f26ee4e9876920821883a0fa12bc7e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167101"
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

**Entry** C++ özniteliği [, MIDL](/windows/win32/Midl/entry) özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

**Girişin**örnek kullanımı için [idl_module](idl-module.md) örneğe bakın.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|`idl_module` özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)
