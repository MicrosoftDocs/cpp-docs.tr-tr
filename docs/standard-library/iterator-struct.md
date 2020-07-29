---
title: iterator Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: b45cdb5c3d4608296cca34ad6a0be6e25b588d28
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222309"
---
# <a name="iterator-struct"></a>iterator Yapısı

Kullanıcı tanımlı Yineleyici sınıfının s ile düzgün çalışmasını sağlamak için kullanılan boş bir temel yapı `iterator_trait` .

## <a name="syntax"></a>Sözdizimi

```cpp
struct iterator {
   typedef Category iterator_category;
   typedef Type value_type;
   typedef Distance difference_type;
   typedef Distance distance_type;
   typedef Pointer pointer;
   typedef Reference reference;
   };
```

## <a name="remarks"></a>Açıklamalar

Şablon yapısı, tüm yineleyiciler için bir temel tür görevi görür. Üye türlerini tanımlar

- `iterator_category`(şablon parametresi için bir eş anlamlı `Category` ).

- `value_type`(şablon parametresi için bir eş anlamlı `Type` ).

- `difference_type`(şablon parametresi için bir eş anlamlı `Distance` ).

- `distance_type`(şablon parametresi için bir eş anlamlı `Distance` )

- `pointer`(şablon parametresi için bir eş anlamlı `Pointer` ).

- `reference`(şablon parametresi için bir eş anlamlı `Reference` ).

`value_type` `pointer` Bir nesnesinin **`const`** `Type` ve başvurusunun bir nesnesinin bir nesnesini belirtse bile sabit bir tür olmamalıdır **`const`** `Type` .

## <a name="example"></a>Örnek

Yineleyici temel sınıfında türlerin nasıl bildirilemeyeceğini ve kullanılacağı hakkında bir örnek için bkz. [iterator_traits](../standard-library/iterator-traits-struct.md) .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
