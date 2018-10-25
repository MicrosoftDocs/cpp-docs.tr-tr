---
title: pragma (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pragma
dev_langs:
- C++
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ac6b00387669f26bbd6cc02f8dd559199dd6bdd5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074182"
---
# <a name="pragma"></a>pragması

Belirtilen dizeyi tırnak işaretleri kullanmanıza gerek kalmadan oluşturulan .idl dosyasına yayar.

## <a name="syntax"></a>Sözdizimi

```cpp
[ pragma(pragma_statement) ];
```

### <a name="parameters"></a>Parametreler

*pragma_statement*<br/>
Oluşturulan .idl dosyasına gitmek istiyorsanız pragması.

## <a name="remarks"></a>Açıklamalar

**Pragma** C++ özniteliği ile aynı işlevlere sahip [pragma](/windows/desktop/Midl/pragma) MIDL özniteliği.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[pack](../../preprocessor/pack.md)