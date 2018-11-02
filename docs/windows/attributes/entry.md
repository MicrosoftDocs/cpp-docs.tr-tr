---
title: Giriş (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: b6c34a603f3ba8abaf070759a22ddf2b8e9c2106
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663261"
---
# <a name="entry"></a>giriş

Dışarı aktarılan işlevin ya da sabit bir modülün dll giriş noktası belirleyerek belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Giriş noktası kimliği.

## <a name="remarks"></a>Açıklamalar

**Giriş** C++ özniteliği ile aynı işlevlere sahip [giriş](/windows/desktop/Midl/entry) MIDL özniteliği.

## <a name="example"></a>Örnek

Örneğin bakın [idl_module](idl-module.md) bir kullanımı örneği için **giriş**.

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|`idl_module` Özniteliği|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)