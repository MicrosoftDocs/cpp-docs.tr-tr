---
title: LCID (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.lcid
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
ms.openlocfilehash: d97ad86e143102c96e87ae0a32245b0c01042501
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032439"
---
# <a name="lcid"></a>lcid

Bir işlev için bir yerel ayar tanımlayıcısı geçirmenize olanak tanır.

## <a name="syntax"></a>Sözdizimi

```cpp
[lcid]
```

## <a name="remarks"></a>Açıklamalar

**LCID** C++ özniteliği işlevselliğini uygulayan [LCID](/windows/desktop/Midl/lcid) MIDL özniteliği. Yerel bir kitaplığı bloğu için uygulamak istediğiniz kullanırsanız **LCID =** `lcid` parametresi [Modülü](module-cpp.md) özniteliği.

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
|**Uygulandığı öğe:**|Parametre arabirimi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Parametre Öznitelikleri](parameter-attributes.md)