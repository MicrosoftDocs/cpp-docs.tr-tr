---
title: library_block (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 76e643cb45d8a87408015e6e0726e47d423147f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459932"
---
# <a name="libraryblock"></a>library_block

IDL kitaplığı bloğu içinde bir yapısı yerleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[library_block]
```

## <a name="remarks"></a>Açıklamalar

Kitaplık bloğu içinde bir yapısı yerleştirdiğinizde, başvurulan olup bağımsız olarak tür kitaplığına geçirilecek emin olun. Varsayılan olarak, yalnızca yapıları tarafından değiştirildi [coclass'ı](coclass.md), [dispinterface](dispinterface.md), ve [idl_module](idl-module.md) öznitelikleri kitaplığı bloğunda yerleştirilir.

## <a name="example"></a>Örnek

Aşağıdaki kodda, özel arabirim kitaplığı bloğunun içine yerleştirilir.

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
|**İçin geçerlidir**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)