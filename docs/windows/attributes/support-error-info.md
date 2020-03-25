---
title: support_error_info (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.support_error_info
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
ms.openlocfilehash: e61ef2efbdc4039f496d7ffbcccc37cc8d111935
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166152"
---
# <a name="support_error_info"></a>support_error_info

Ayrıntılı hataları döndürmek için destek uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>Parametreler

*error_interface*<br/>
`IErrorInfo`uygulayan arabirimin tanımlayıcısı.

## <a name="remarks"></a>Açıklamalar

**Support_error_info** C++ özniteliği, hedef nesnenin istemciye karşılaştığı ayrıntılı, bağlamsal hataları döndürmek için destek uygular. Nesnenin hataları desteklemesi için, `IErrorInfo` arabirimi yöntemlerinin nesne tarafından uygulanması gerekir. Daha fazla bilgi için bkz. [IDispatch ve IErrorInfo destekleme](../../atl/supporting-idispatch-and-ierrorinfo.md).

Bu öznitelik, [ıupporterrorınfoımpl](../../atl/reference/isupporterrorinfoimpl-class.md) sınıfını hedef nesnesine bir temel sınıf olarak ekler. Bu, varsayılan `ISupportErrorInfo` bir uygulamayla sonuçlanır ve tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.

## <a name="example"></a>Örnek

Aşağıdaki kod, `CMyClass` nesnesine `ISupportErrorInfo` arabirimi için varsayılan destek ekler.

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
|**Uygulama hedefi**|**class**|
|**Tekrarlanabilir**|Yes|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)
