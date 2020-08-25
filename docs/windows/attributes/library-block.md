---
title: library_block (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 13988abc12eb0b136dfc8d2c0d597005b56f0526
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834122"
---
# <a name="library_block"></a>library_block

IDL kitaplık bloğunun içine bir yapı koyar.

## <a name="syntax"></a>Syntax

```cpp
[library_block]
```

## <a name="remarks"></a>Açıklamalar

Kitaplık bloğunun içine bir yapı yerleştirdiğinizde, başvurulduğuna bakılmaksızın bunun tür kitaplığına geçirilmesini de sağlayabilirsiniz. Varsayılan olarak, yalnızca [coclass](coclass.md), [dispınterface](dispinterface.md)ve [idl_module](idl-module.md) öznitelikleri tarafından değiştirilen yapılar kitaplık bloğuna yerleştirilir.

## <a name="example"></a>Örnek

Aşağıdaki kodda, kitaplık bloğunun içine özel bir arabirim yerleştirilir.

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
```

## <a name="requirements"></a>Gereksinimler

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)
