---
title: library_block (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 405cc1cd5af7dcd689e833764f3da2fdc6d5f703
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214779"
---
# <a name="library_block"></a>library_block

IDL kitaplık bloğunun içine bir yapı koyar.

## <a name="syntax"></a>Sözdizimi

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

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)
