---
title: appobject (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.appobject
dev_langs:
- C++
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dcd863cabb0f2cc58d25ea98503637592a994794
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789834"
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
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](idl-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)  