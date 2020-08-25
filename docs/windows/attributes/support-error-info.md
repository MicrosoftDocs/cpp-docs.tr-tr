---
title: support_error_info (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.support_error_info
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
ms.openlocfilehash: cf02af793b97c55de4c52280ad2795a460a98d9f
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832184"
---
# <a name="support_error_info"></a>support_error_info

Ayrıntılı hataları döndürmek için destek uygular.

## <a name="syntax"></a>Söz dizimi

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>Parametreler

*error_interface*<br/>
Uygulayan arabirimin tanımlayıcısı `IErrorInfo` .

## <a name="remarks"></a>Açıklamalar

C++ özniteliği **Support_error_info** , hedef nesnenin istemciye karşılaştığı ayrıntılı, bağlamsal hataları döndürme desteğini uygular. Nesnenin hataları desteklemesi için, `IErrorInfo` Arabirim yöntemlerinin nesne tarafından uygulanması gerekir. Daha fazla bilgi için bkz. [IDispatch ve IErrorInfo destekleme](../../atl/supporting-idispatch-and-ierrorinfo.md).

Bu öznitelik, [ıupporterrorınfoımpl](../../atl/reference/isupporterrorinfoimpl-class.md) sınıfını hedef nesnesine bir temel sınıf olarak ekler. Bu, varsayılan bir uygulaması ile sonuçlanır `ISupportErrorInfo` ve tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki kod, nesnesine arabirim için varsayılan destek ekler `ISupportErrorInfo` `CMyClass` .

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**|
|**Tekrarlanabilir**|Yes|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM öznitelikleri](com-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)
