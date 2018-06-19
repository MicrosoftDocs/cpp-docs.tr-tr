---
title: iterator yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e9cd414e2e6f23cb2fe44e6de4b5f53b33ef3555
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857889"
---
# <a name="iterator-struct"></a>iterator Yapısı

Bir kullanıcı tarafından tanımlanan yineleyici sınıf düzgün ile çalıştığından emin olmak için kullanılan boş bir temel yapı **iterator_trait**s.

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

Şablon yapısı tüm yineleyiciler için temel tür olarak görev yapar. Üye türleri tanımlar

- `iterator_category` (şablon parametresi için bir eş anlamlı `Category`).

- `value_type` (şablon parametresi için bir eş anlamlı **türü**).

- `difference_type` (şablon parametresi için bir eş anlamlı `Distance`).

- `distance_type` (şablon parametresi için bir eş anlamlı `Distance`)

- `pointer` (şablon parametresi için bir eş anlamlı `Pointer`).

- `reference` (şablon parametresi için bir eş anlamlı `Reference`).

Unutmayın `value_type` bir sabit türü olsa bile olmamalıdır **işaretçi** const nesnenin noktalarda **türü** ve başvurusu bir nesnenin const atar **türü**.

## <a name="example"></a>Örnek

Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) bildirme ve türleri yineleyici taban sınıf içinde nasıl kullanılacağını gösteren bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
