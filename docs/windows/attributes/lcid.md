---
title: LCID (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.lcid
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
ms.openlocfilehash: 7533cd9b269a879c5c2f061dcdfc632b1b27c871
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834186"
---
# <a name="lcid"></a>lcid

Bir işleve yerel ayar tanımlayıcıyı geçirmenize olanak sağlar.

## <a name="syntax"></a>Syntax

```cpp
[lcid]
```

## <a name="remarks"></a>Açıklamalar

**LCID** C++ özniteliği, [LCID](/windows/win32/Midl/lcid) MIDL özniteliğinin işlevlerini uygular. Bir kitaplık bloğu için yerel ayar uygulamak istiyorsanız, modül özniteliğinde **LCID =** `lcid` parametresini kullanın [module](module-cpp.md) .

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Arabirim parametresi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)
