---
title: dışarı aktarC++ (com özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 6264db037069f5fc6b858bdd466ce6c68b814a84
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167050"
---
# <a name="export"></a>dışarı aktar

Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.

## <a name="syntax"></a>Sözdizimi

```cpp
[export]
```

## <a name="remarks"></a>Açıklamalar

**Dışarı aktarma** C++ özniteliği bir veri yapısının. IDL dosyasına yerleştirilmesine ve daha sonra tür kitaplığında, herhangi bir dille kullanılabilmesini sağlayan ikili uyumlu bir biçimde kullanılabilir hale gelmesine neden olur.

Sınıf yalnızca ortak üyelere sahip olsa bile, bir sınıfa **dışa aktarma** özniteliğini uygulayamazsınız (bir **yapının**eşdeğeri).

Adlandırılmamış bir **enum** veya **struct**dışa aktardığınızda, buna **__unnamed**<em>x</em>ile başlayan bir ad verilir; burada *x* sıralı bir sayıdır.

Dışarı aktarma için geçerli olan tür tanımları 'lar temel türler, yapılar, birleşimler, numaralandırmalar veya tür tanımlayıcılarıdır.  Daha fazla bilgi için bkz. [typedef](/windows/win32/Midl/typedef) .

## <a name="example"></a>Örnek

Aşağıdaki kod, **dışarı aktarma** özniteliğinin nasıl kullanılacağını gösterir:

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
|**Uygulama hedefi**|**Union**, **typedef**, **enum**, **struct**veya **Interface**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Öznitelikleri](compiler-attributes.md)<br/>
[Typedef, Enum, Union ve Struct Öznitelikleri](typedef-enum-union-and-struct-attributes.md)
