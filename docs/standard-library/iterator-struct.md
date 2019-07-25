---
title: iterator Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 64c9be76cb92d818e40714dd141ded3a8cc17c8a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455613"
---
# <a name="iterator-struct"></a>iterator Yapısı

Kullanıcı tanımlı Yineleyici sınıfının s ile `iterator_trait`düzgün çalışmasını sağlamak için kullanılan boş bir temel yapı.

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

- `iterator_category`(şablon parametresi `Category`için bir eş anlamlı).

- `value_type`(şablon parametresi `Type`için bir eş anlamlı).

- `difference_type`(şablon parametresi `Distance`için bir eş anlamlı).

- `distance_type`(şablon parametresi `Distance`için bir eş anlamlı)

- `pointer`(şablon parametresi `Pointer`için bir eş anlamlı).

- `reference`(şablon parametresi `Reference`için bir eş anlamlı).

`pointer`  **Const** ve Reference nesne bir const`Type`nesnesinin bir nesnesini belirtse bile sabit bir tür olmamalıdır. `Type` `value_type`

## <a name="example"></a>Örnek

Yineleyici temel sınıfında türlerin nasıl bildirilemeyeceğini ve kullanılacağı hakkında bir örnek için bkz. [iterator_traits](../standard-library/iterator-traits-struct.md) .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
