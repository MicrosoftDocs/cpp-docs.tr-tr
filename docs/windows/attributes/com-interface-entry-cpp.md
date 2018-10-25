---
title: com_interface_entry (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.com_interface_entry
dev_langs:
- C++
helpviewer_keywords:
- com_interface_entry attribute
ms.assetid: 10368f81-b99b-4a0f-ba4f-a142e6911a5c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6ccd3277b5ad627c6956e6f5620ee6aed1640cc5
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074013"
---
# <a name="cominterfaceentry-c"></a>com_interface_entry (C++)

COM eşlemesi hedef sınıfın arabirim giriş ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
[ com_interface_entry(
  com_interface_entry) ]
```

### <a name="parameters"></a>Parametreler

*com_interface_entry*<br/>
Girişinin gerçek metni içeren bir dize. Olası değerler listesi için bkz. [COM_INTERFACE_ENTRY makroları](../../atl/reference/com-interface-entry-macros.md).

## <a name="remarks"></a>Açıklamalar

**Com_interface_entry** C++ özniteliği hedef nesnenin COM arabirimi haritayı unabridged içeriğini bir karakter dizesi ekler. Öznitelik bir kez hedef nesneye uygulanırsa, giriş varolan bir arabirim eşlemesini başına içine eklenir. Öznitelik tekrar tekrar aynı hedef nesneye uygulanırsa, girişleri alındıkları sırayla arabirim eşlemesi başına eklenir.

Bu öznitelik gerektiren [coclass'ı](coclass.md), [ProgID](progid.md), veya [vi_progid](vi-progid.md) özniteliği (ya da bunlardan birini anlamına gelir. başka bir öznitelik) da uygulanabilir aynı öğeye. Herhangi bir tek öznitelik kullandıysanız, diğer iki otomatik olarak uygulanır. Örneğin, varsa `progid` uygulanan `vi_progid` ve `coclass` de uygulanır.

Çünkü ilk kullanımını **com_interface_entry** arabirim eşlemesi başında eklenecek yeni arabirim neden şu COM_INTERFACE_ENTRY türlerden biri olmalıdır:

- COM_INTERFACE_ENTRY

- COM_INTERFACE_ENTRY_IID

- COM_INTERFACE_ENTRY2

- COM_INTERFACE_ENTRY2_IID

İlave kullanımlar **com_interface_entry** özniteliği, desteklenen tüm COM_INTERFACE_ENTRY türleri kullanabilirsiniz.

ATL ilk giriş kimliği olarak arabirim eşlemesine kullandığından bu kısıtlama gereklidir `IUnknown`; bu nedenle, giriş geçerli bir arabirimi olmalıdır. Örneğin, aşağıdaki kod örneği arabirim eşlemesi ilk giriş gerçek bir COM arabirimi belirtmediğinden geçersiz.

```cpp
[ coclass, com_interface_entry =
    "COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"
]
   class CMyClass
   {
   };
```

## <a name="example"></a>Örnek

Aşağıdaki kod, iki girişe mevcut COM arabirimi haritaya ekler `CMyBaseClass`. İlk standart bir arabirimdir ve ikinci gizler `IDebugTest` arabirimi.

```cpp
// cpp_attr_ref_com_interface_entry.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name ="ldld")];

[ object,
  uuid("7dbebed3-d636-4917-af62-c767a720a5b9")]
__interface IDebugTest{};

[ object,
  uuid("2875ceac-f94b-4087-8e13-d13dc167fcfc")]
__interface IMyClass{};

[ coclass,
  com_interface_entry ("COM_INTERFACE_ENTRY (IMyClass)"),
  com_interface_entry ("COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)"),
  uuid("b85f8626-e76e-4775-b6a0-4826a9e94af2")
]

class CMyClass: public IMyClass, public IDebugTest
{
};
```

Elde edilen COM Nesne eşleme için `CMyBaseClass` aşağıdaki gibidir:

```cpp
BEGIN_COM_MAP(CMyClass)
    COM_INTERFACE_ENTRY (IMyClass)
    COM_INTERFACE_ENTRY_NOINTERFACE(IDebugTest)
    COM_INTERFACE_ENTRY(IMyClass)
    COM_INTERFACE_ENTRY2(IDispatch, IMyClass)
    COM_INTERFACE_ENTRY(IDebugTest)
    COM_INTERFACE_ENTRY(IProvideClassInfo)
END_COM_MAP()
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**sınıf**, **yapısı**|
|**Tekrarlanabilir**|Evet|
|**Gerekli öznitelikleri**|Bir veya daha fazlasını: `coclass`, `progid`, veya `vi_progid`.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[COM Öznitelikleri](com-attributes.md)<br/>
[Sınıf Öznitelikleri](class-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)