---
title: library_block | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.library_block
dev_langs:
- C++
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 39067dd242fece7abb284448104115ac9a5ce4fd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404377"
---
# <a name="libraryblock"></a>library_block

IDL kitaplığı bloğu içinde bir yapısı yerleştirir.

## <a name="syntax"></a>Sözdizimi

```cpp
[library_block]
```

## <a name="remarks"></a>Açıklamalar

Kitaplık bloğu içinde bir yapısı yerleştirdiğinizde, başvurulan olup bağımsız olarak tür kitaplığına geçirilecek emin olun. Varsayılan olarak, yalnızca yapıları tarafından değiştirildi [coclass'ı](../windows/coclass.md), [dispinterface](../windows/dispinterface.md), ve [idl_module](../windows/idl-module.md) öznitelikleri kitaplığı bloğunda yerleştirilir.

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

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](../windows/compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)  