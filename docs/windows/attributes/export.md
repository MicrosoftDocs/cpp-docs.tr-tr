---
title: Export (C++ COM özniteliği)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 4854789d9f977b3b747fd9b546cb92642942be88
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845282"
---
# <a name="export"></a>dışarı aktarma

Veri yapısının. IDL dosyasına yerleştirilmesine neden olur.

## <a name="syntax"></a>Syntax

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

| Öznitelik bağlamı | Değer |
|-|-|
|**Şunlara uygulanır**|**`union`**,,, **`typedef`** **`enum`** **`struct`** veya **`interface`**|
|**Tekrarlanabilir**|Hayır|
|**Gerekli öznitelikler**|Yok|
|**Geçersiz öznitelikler**|Yok|

Daha fazla bilgi için bkz. [öznitelik bağlamları](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici öznitelikleri](compiler-attributes.md)<br/>
[TypeDef, Enum, Union ve struct öznitelikleri](typedef-enum-union-and-struct-attributes.md)
