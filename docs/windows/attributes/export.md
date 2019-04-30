---
title: dışarı aktarma (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 5ffa4283b8a2b265809d06b72be96e217cf8bf9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409622"
---
# <a name="export"></a>dışarı aktar

Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.

## <a name="syntax"></a>Sözdizimi

```cpp
[export]
```

## <a name="remarks"></a>Açıklamalar

**Dışarı** C++ öznitelik, bir veri yapısı .idl dosyasına yerleştirilmesini ve herhangi bir dil ile kullanmak için kullanılabilir hale getirir ikili ile uyumlu bir biçimde tür kitaplığında kullanılabilir olması için neden olur.

Uygulayamazsınız **dışarı** sınıfı yalnızca Genel üyeler olsa bile bir sınıf özniteliği (denk bir **yapı**).

Adlandırılmamış bir dışa aktarmak istemiyorsanız **enum** veya **yapı**, ile başlayan bir ad verilir **__unnamed**<em>x</em>burada *x* sıralı bir sayıdır.

Tür tanımları dışarı aktarma için geçerli olan temel türleri, yapılar, birleşimler, numaralandırmalar veya tanımlayıcıları yazın.  Bkz: [typedef](/windows/desktop/Midl/typedef) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki kod nasıl kullanılacağını gösterir **dışarı** özniteliği:

```cpp
// cpp_attr_ref_export.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```

## <a name="requirements"></a>Gereksinimler

### <a name="attribute-context"></a>Öznitelik bağlamı

|||
|-|-|
|**İçin geçerlidir**|**birleşim**, **typedef**, **enum**, **yapı**, veya **arabirimi**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikleri**|Yok.|
|**Geçersiz öznitelikler**|Yok.|

Daha fazla bilgi için [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)