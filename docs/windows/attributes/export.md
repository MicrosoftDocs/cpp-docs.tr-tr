---
title: Dışarı Aktar (C++ COM özniteliği) | Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a636b7d4c943896bcd1e5e7b3580c2d3f7410fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48789839"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)  