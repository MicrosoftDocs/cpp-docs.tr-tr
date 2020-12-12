---
description: 'Hakkında daha fazla bilgi edinin: LCID'
title: LCID (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.lcid
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
ms.openlocfilehash: 2af34574539372a07daadc48874316b0b268f317
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329851"
---
# <a name="lcid"></a>lcid

Bir işleve yerel ayar tanımlayıcıyı geçirmenize olanak sağlar.

## <a name="syntax"></a>Syntax

```cpp
[lcid]
```

## <a name="remarks"></a>Açıklamalar

**LCID** C++ özniteliği, [LCID](/windows/win32/Midl/lcid) MIDL özniteliğinin işlevlerini uygular. Bir kitaplık bloğu için yerel ayar uygulamak istiyorsanız, modül özniteliğinde **LCID =** `lcid` parametresini kullanın [](module-cpp.md) .

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
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Parametre öznitelikleri](parameter-attributes.md)
