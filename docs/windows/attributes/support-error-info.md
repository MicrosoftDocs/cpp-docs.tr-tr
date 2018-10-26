---
title: support_error_info (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0d86b31823ec31461f953c7cfc16a5774f215fd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067169"
---
# <a name="supporterrorinfo"></a>support_error_info

Uygular, ayrıntılı hatalar döndürmek için destek.

## <a name="syntax"></a>Sözdizimi

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>Parametreler

*error_interface*<br/>
Arabirimi uygulama tanımlayıcısını `IErrorInfo`.

## <a name="remarks"></a>Açıklamalar

**Support_error_info** C++ özniteliği hedef nesnesi istemci tarafından karşılaşılan ayrıntılı ve bağlamsal hataları döndürmek için destek uygular. Hata, yöntemlerini desteklemek nesne için `IErrorInfo` arabirimi nesne tarafından uygulanan gerekir. Daha fazla bilgi için [destekleyen IDispatch ve IErrorInfo](../../atl/supporting-idispatch-and-ierrorinfo.md).

Bu öznitelik ekler [Isupporterrorınfoımpl](../../atl/reference/isupporterrorinfoimpl-class.md) hedef nesneye bir temel sınıf olarak sınıf. Bu varsayılan uygulamasında sonuçları `ISupportErrorInfo` ve tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki kod, varsayılan desteği ekler `ISupportErrorInfo` arabirimini `CMyClass` nesne.

```cpp
// cpp_attr_ref_support_error_info.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="mymod")];
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]
__interface IMyErrors
{
};

[ coclass, support_error_info("IMyErrors"),
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]
class CMyClass
{
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**class**|
|**Tekrarlanabilir**|Evet|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)