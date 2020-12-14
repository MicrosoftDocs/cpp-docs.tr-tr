---
description: 'Daha fazla bilgi edinin: Yineleyici yapısı'
title: iterator Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 81a35fd749b3393a0235fdac8c4bf13a1ef5af79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254332"
---
# <a name="iterator-struct"></a>iterator Yapısı

Kullanıcı tanımlı Yineleyici sınıfının s ile düzgün çalışmasını sağlamak için kullanılan boş bir temel yapı `iterator_trait` .

## <a name="syntax"></a>Syntax

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

- `iterator_category` (şablon parametresi için bir eş anlamlı `Category` ).

- `value_type` (şablon parametresi için bir eş anlamlı `Type` ).

- `difference_type` (şablon parametresi için bir eş anlamlı `Distance` ).

- `distance_type` (şablon parametresi için bir eş anlamlı `Distance` )

- `pointer` (şablon parametresi için bir eş anlamlı `Pointer` ).

- `reference` (şablon parametresi için bir eş anlamlı `Reference` ).

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
