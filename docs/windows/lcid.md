---
title: LCID | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.lcid
dev_langs:
- C++
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3bf5b229baa953a8e3431a35f4449fbae87a4d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46405651"
---
# <a name="lcid"></a>lcid

Bir işlev için bir yerel ayar tanımlayıcısı geçirmenize olanak tanır.

## <a name="syntax"></a>Sözdizimi

```cpp
[lcid]
```

## <a name="remarks"></a>Açıklamalar

**LCID** C++ özniteliği işlevselliğini uygulayan [LCID](/windows/desktop/Midl/lcid) MIDL özniteliği. Yerel bir kitaplığı bloğu için uygulamak istediğiniz kullanırsanız **LCID =** `lcid` parametresi [Modülü](../windows/module-cpp.md) özniteliği.

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
|**İçin geçerlidir**|Parametre arabirimi|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)<br/>
[Parametre Öznitelikleri](../windows/parameter-attributes.md)  