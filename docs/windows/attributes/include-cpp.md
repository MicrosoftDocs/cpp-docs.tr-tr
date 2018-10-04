---
title: (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.include
dev_langs:
- C++
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 97c7ca1f808beb7e0658338dac77819455f9ed84
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789880"
---
# <a name="include-c"></a>include (C++)

Oluşturulan .idl dosyasına eklenecek bir veya daha fazla üst bilgi dosyaları belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Parametreler

*header_fıle*<br/>
Oluşturulan .idl dosyasına dahil istediğiniz bir dosya adı.

## <a name="remarks"></a>Açıklamalar

**Dahil** C++ öznitelik neden olan bir `#include` altına yerleştirilecek deyimi `import "docobj.idl"` oluşturulan .idl dosyasındaki deyimi.

**Dahil** C++ özniteliği ile aynı işlevlere sahip [dahil](/windows/desktop/Midl/include) MIDL özniteliği.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği nasıl kullanılacağını gösterir **dahil**. Bu örnekte, yalnızca dosya include.h içeren bir `#include` deyimi.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
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

[IDL öznitelikleri](idl-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)  