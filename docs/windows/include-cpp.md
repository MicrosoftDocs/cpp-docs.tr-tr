---
title: (C++) ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 8fe604074b843e7c0b76c2e671e0abd9e40770a7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598466"
---
# <a name="include-c"></a>include (C++)

Oluşturulan .idl dosyasına eklenecek bir veya daha fazla üst bilgi dosyaları belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
[ include(
   header_file
) ];
```

### <a name="parameters"></a>Parametreler

*header_fıle*  
Oluşturulan .idl dosyasına dahil istediğiniz bir dosya adı.

## <a name="remarks"></a>Açıklamalar

**Dahil** C++ öznitelik neden olan bir `#include` altına yerleştirilecek deyimi `import "docobj.idl"` oluşturulan .idl dosyasındaki deyimi.

**Dahil** C++ özniteliği ile aynı işlevlere sahip [dahil](http://msdn.microsoft.com/library/windows/desktop/aa367052) MIDL özniteliği.

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

Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).

## <a name="see-also"></a>Ayrıca Bkz.

[IDL öznitelikleri](../windows/idl-attributes.md)  
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importidl](../windows/importidl.md)  
[includelib](../windows/includelib-cpp.md)  
[importlib](../windows/importlib.md)  