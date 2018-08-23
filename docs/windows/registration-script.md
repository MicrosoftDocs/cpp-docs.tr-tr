---
title: registration_script | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 997b8bc01424b102551815f19ff9a487113e5f6b
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601019"
---
# <a name="registrationscript"></a>registration_script

Belirtilen özel kayıt betiği çalıştırır.

## <a name="syntax"></a>Sözdizimi

```cpp
[ registration_script(
   script
) ]
```

### <a name="parameters"></a>Parametreler

*komut dosyası*  
Özel kayıt betiği (.rgs) dosyasının tam yolu. Değerini **hiçbiri**, gibi `script = "none"`, coclass'ı hiçbir kayıt gereksinimleri sahip olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

**Registration_script** C++ özniteliği tarafından belirtilen özel kayıt betiği yürüten *betik*. Bu öznitelik belirtilmezse (Bileşen kaydetmeye yönelik bilgileri içeren) bir standart .rgs dosyası kullanılır. .Rgs dosyaları hakkında daha fazla bilgi için bkz. [ATL kayıt defteri bileşeni (Kaydedici)](../atl/atl-registry-component-registrar.md).

Bu öznitelik gerektiren [coclass'ı](../windows/coclass.md), [ProgID](../windows/progid.md), veya [vi_progid](../windows/vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye.

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

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](../windows/com-attributes.md)  
[Sınıf Öznitelikleri](../windows/class-attributes.md)  
[rdx](../windows/rdx.md)  