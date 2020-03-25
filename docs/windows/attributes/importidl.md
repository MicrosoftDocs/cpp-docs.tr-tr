---
title: ımportıdl (C++ com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 6e41a98bef079c92b6df6e7eff203301aa9ceae4
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166828"
---
# <a name="importidl"></a>importidl

Belirtilen. IDL dosyasını oluşturulan. IDL dosyasına ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>Parametreler

*idl_file*<br/>
Uygulamanız için oluşturulacak. IDL dosyası ile birleştirmek istediğiniz. IDL dosyasının adını tanımlar.

## <a name="remarks"></a>Açıklamalar

**Importıdl** C++ özniteliği, *idl_file*bölümü, programınızın üretilen. IDL dosyasına ve kitaplık bölümüne ( *idl_file*) programınızın oluşturulan. IDL dosyasının Kitaplık bölümüne koyar.

Örneğin, üretilen. IDL dosyanıza birlikte kodlanmış bir. IDL dosyası kullanmak istiyorsanız, **ımportidl**kullanmak isteyebilirsiniz.

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
|**Uygulama hedefi**|Yerdeki|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
