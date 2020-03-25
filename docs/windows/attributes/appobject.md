---
title: appobject (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: ebbb3ce71dc9b947ef49a42ee41a5ce2d5abbb34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168518"
---
# <a name="appobject"></a>appobject

Bir tam. exe uygulamasıyla ilişkili bir uygulama nesnesi olarak coclass 'ı tanımlar ve coclass 'ın işlevlerinin ve özelliklerinin bu [tür kitaplığında](../../mfc/automation-clients-using-type-libraries.md)genel olarak kullanılabildiğini gösterir.

## <a name="syntax"></a>Sözdizimi

```cpp
[appobject]
```

## <a name="remarks"></a>Açıklamalar

**Appobject** C++ özniteliği [appobject](/windows/win32/Midl/appobject) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **appobject**içeren bir öznitelik bloğunun önünde bir basit sınıf tanımını gösterir:

```cpp
// cpp_attr_ref_appobject.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];

[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]
__interface ICustom {};

[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]
class A : public ICustom {
   int i;
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|**sınıf**, **Yapı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|`coclass`|
|**Geçersiz öznitelikler**|Hiçbiri|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)
