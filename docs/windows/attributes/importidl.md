---
title: importidl (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 9db62d4f2a36b8cc0592c924b113077a758915c0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029920"
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
|**Uygulandığı öğe:**|Her yerde|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|None|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Tek Başına Öznitelikler](stand-alone-attributes.md)<br/>
[içeri aktar](import.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)