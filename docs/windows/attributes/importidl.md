---
title: ımportıdl (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 8f3c2c5c67ac216d096d1082814c561698f3f732
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842253"
---
# <a name="importidl"></a>importidl

Belirtilen. IDL dosyasını oluşturulan. IDL dosyasına ekler.

## <a name="syntax"></a>Söz dizimi

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|Her yer|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[Tek başına öznitelikler](stand-alone-attributes.md)<br/>
[aktarmaya](import.md)<br/>
[importlib](importlib.md)<br/>
[içeriyor](include-cpp.md)<br/>
[INCLUDELIB](includelib-cpp.md)
