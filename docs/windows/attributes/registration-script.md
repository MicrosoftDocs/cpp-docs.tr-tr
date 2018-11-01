---
title: registration_script (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.registration_script
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
ms.openlocfilehash: 304d4139cb1adbbb7c345cd3ce6f7fc985907712
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50555135"
---
# <a name="registrationscript"></a>registration_script

Belirtilen özel kayıt betiği çalıştırır.

## <a name="syntax"></a>Sözdizimi

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>Parametreler

*komut dosyası*<br/>
Özel kayıt betiği (.rgs) dosyasının tam yolu. Değerini **hiçbiri**, gibi `script = "none"`, coclass'ı hiçbir kayıt gereksinimleri sahip olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

**Registration_script** C++ özniteliği tarafından belirtilen özel kayıt betiği yürüten *betik*. Bu öznitelik belirtilmezse (Bileşen kaydetmeye yönelik bilgileri içeren) bir standart .rgs dosyası kullanılır. .Rgs dosyaları hakkında daha fazla bilgi için bkz. [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).

Bu öznitelik gerektiren [coclass'ı](coclass.md), [ProgID](progid.md), veya [vi_progid](vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye.

## <a name="example"></a>Örnek

Aşağıdaki kod, bileşen cpp_attr_ref_registration_script.rgs adlı bir kayıt defteri betik sahip olduğunu belirtir.

```cpp
// cpp_attr_ref_registration_script.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="REG")];

[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]
__interface IFace {};

// requires "cpp_attr_ref_registration_script.rgs"
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]
class CMyClass:public IFace {};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Bir veya daha fazlasını: `coclass`, `progid`, veya `vi_progid`.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[rdx](rdx.md)