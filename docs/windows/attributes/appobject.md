---
description: 'Daha fazla bilgi edinin: appobject'
title: appobject (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: b371b9726e3a750ef5d40ebe5abae219b473bb02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205466"
---
# <a name="appobject"></a>appobject

Bir tam. exe uygulamasıyla ilişkili bir uygulama nesnesi olarak coclass 'ı tanımlar ve coclass 'ın işlevlerinin ve özelliklerinin bu [tür kitaplığında](../../mfc/automation-clients-using-type-libraries.md)genel olarak kullanılabildiğini gösterir.

## <a name="syntax"></a>Syntax

```cpp
[appobject]
```

## <a name="remarks"></a>Açıklamalar

**Appobject** C++ özniteliği, [appobject](/windows/win32/Midl/appobject) MIDL özniteliğiyle aynı işlevselliğe sahiptir.

## <a name="example"></a>Örnek

Aşağıdaki kod, **appobject** içeren bir öznitelik bloğunun önünde bir basit sınıf tanımını gösterir:

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`class`**, **`struct`**|
|**Yinelenebilir**|Hayır|
|**Gerekli öznitelikler**|`coclass`|
|**Geçersiz öznitelikler**|Yok|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf öznitelikleri](class-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)
