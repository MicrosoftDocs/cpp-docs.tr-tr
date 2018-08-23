---
title: importidl | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bb6c1bd23eaf705f6ceb57e5fc4ea3354c0ddfc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571364"
---
# <a name="importidl"></a>importidl

Belirtilen .idl dosyası oluşturulan .idl dosyasına ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
[ importidl(
   idl_file
) ];
```

### <a name="parameters"></a>Parametreler

*idl_file*  
Uygulamanız için oluşturulacak .idl dosyası ile birleştirmek istediğiniz .idl dosyasının adını tanımlar.

## <a name="remarks"></a>Açıklamalar

**İmportidl** C++ özniteliği yerleştirir kitaplığı bloğu dışında bölümü (içinde *idl_file*) programınızın oluşturulan .idl dosyasının ve kitaplık bölümü (içinde *idl_file*) kitaplığa programınızın bölümünü .idl dosyası oluşturulur.

Kullanmak istediğiniz **importidl**, örneğin, bir .idl el kodlanmış ile oluşturulan .idl dosyası kullanmak istiyorsanız.

## <a name="example"></a>Örnek

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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

[Derleyici Öznitelikleri](../windows/compiler-attributes.md)  
[Tek Başına Öznitelikler](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importlib](../windows/importlib.md)  
[İçerir](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)  