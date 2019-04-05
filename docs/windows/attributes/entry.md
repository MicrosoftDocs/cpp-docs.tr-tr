---
title: Giriş (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 703a55ee7c56b64a5b168016770508508bab09e0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036308"
---
# <a name="entry"></a>giriş

Dışarı aktarılan işlevin ya da sabit bir modülün dll giriş noktası belirleyerek belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Parametreler

*kimlik*<br/>
Giriş noktası kimliği.

## <a name="remarks"></a>Açıklamalar

**Giriş** C++ özniteliği ile aynı işlevlere sahip [giriş](/windows/desktop/Midl/entry) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [idl_module](idl-module.md) bir kullanımı örneği için **giriş**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|`idl_module` özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)