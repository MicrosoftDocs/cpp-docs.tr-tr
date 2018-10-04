---
title: importidl (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: d1c022a48ef5510f67355af3af1ff0a0e98ad4c4
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789863"
---
# <a name="importidl"></a>importidl

Belirtilen .idl dosyası oluşturulan .idl dosyasına ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>Parametreler

*idl_file*<br/>
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

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[İçerir](include-cpp.md)<br/>
[includelib](includelib-cpp.md)  