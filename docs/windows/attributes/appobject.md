---
title: appobject (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: 8219c8fdd1b1df93f92fc6c1d0324a2475d3384b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034689"
---
# <a name="appobject"></a>appobject

Bir tam .exe uygulamayla ilişkili olan ve coclass'ı özellikleri ve işlevleri bu küresel olarak kullanılabilir olduğunu gösterir bir uygulama nesnesi olarak coclass'ı tanımlayan [tür kitaplığı](../../mfc/automation-clients-using-type-libraries.md).

## <a name="syntax"></a>Sözdizimi

```cpp
[appobject]
```

## <a name="remarks"></a>Açıklamalar

**Appobject** C++ özniteliği ile aynı işlevlere sahip [appobject](/windows/desktop/Midl/appobject) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kodu içeren bir öznitelik bloğu tarafından öncesinde bir basit sınıf tanımını gösterir **appobject**:

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
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|`coclass`|
|**Geçersiz öznitelikler**|None|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)