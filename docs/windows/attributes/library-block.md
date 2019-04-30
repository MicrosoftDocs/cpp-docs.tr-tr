---
title: library_block (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 219f6a89dd7f80246e0337c2ef3bcad43540b165
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409258"
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
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)