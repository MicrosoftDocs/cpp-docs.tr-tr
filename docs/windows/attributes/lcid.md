---
title: LCID (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.lcid
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
ms.openlocfilehash: bb9e44d34c675e4f5d955c5f422a6dd35259ec8d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214805"
---
# <a name="lcid"></a>lcid

Bir işleve yerel ayar tanımlayıcıyı geçirmenize olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
[lcid]
```

## <a name="remarks"></a>Açıklamalar

**LCID** C++ özniteliği, [LCID](/windows/win32/Midl/lcid) MIDL özniteliğinin işlevlerini uygular. Bir kitaplık bloğu için yerel ayar uygulamak istiyorsanız, [Modül](module-cpp.md) özniteliğinde **LCID =** `lcid` parametresini kullanın.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_lcid.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];
typedef long HRESULT;

[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]
__interface IStatic {
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Arabirim parametresi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)
