---
title: v1_enum (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.v1_enum
helpviewer_keywords:
- v1_enum attribute
ms.assetid: 2fe92d92-81b9-4a1c-b6ce-437d0eb770ca
ms.openlocfilehash: 08654eed7ad467dc22d2cbbf811c9169e5292f16
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024575"
---
# <a name="v1enum"></a>v1_enum

Belirtilen listeden seçimli türü 16-bit varsayılan yerine bir 32-bit varlık olarak iletilmesi yönlendirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[v1_enum]
```

## <a name="remarks"></a>Açıklamalar

**V1_enum** C++ özniteliği ile aynı işlevlere sahip [v1_enum](/windows/desktop/Midl/v1-enum) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod, bir kullanımını göstermektedir. **v1_enum**:

```cpp
// cpp_attr_ref_v1_enum.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export, v1_enum]
enum eList {
   e1 = 1, e2 = 2
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulandığı öğe:**|Numaralandırılmış tür|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Öznitelik bağlamları hakkında daha fazla bilgi için bkz: [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[IDL Öznitelikleri](idl-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)