---
title: Export (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: ae7c426466bfaf4a325ba1cafe30c8ca74f8ef95
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228082"
---
# <a name="export"></a>dışarı aktarma

Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.

## <a name="syntax"></a>Sözdizimi

```cpp
[export]
```

## <a name="remarks"></a>Açıklamalar

**`[export]`** C++ özniteliği bir veri yapısının. IDL dosyasına yerleştirilmesine ve daha sonra tür kitaplığında, herhangi bir dille kullanılabilmesini sağlayan ikili uyumlu bir biçimde kullanılabilir hale gelmesine neden olur.

**`[export]`** Sınıf yalnızca ortak üyelere sahip olsa bile, özniteliğe bir sınıfa uygulayamazsınız (bir öğesinin eşdeğeri **`struct`** ).

Adlandırılmamış bir veya dışa aktardığınızda **`enum`** **`struct`** , **__unnamed**<em>x</em>ile başlayan bir ad verilir, burada *x* sıralı bir sayıdır.

Dışarı aktarma için geçerli olan tür tanımları 'lar temel türler, yapılar, birleşimler, numaralandırmalar veya tür tanımlayıcılarıdır.  [`typedef`](/windows/win32/Midl/typedef)Daha fazla bilgi için bkz..

## <a name="example"></a>Örnek

Aşağıdaki kod özniteliğin nasıl kullanılacağını gösterir **`[export]`** :

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
|**Şunlara uygulanır**|**`union`**,,, **`typedef`** **`enum`** **`struct`** veya**`interface`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Hiçbiri|
|**Geçersiz öznitelikler**|Hiçbiri|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)
