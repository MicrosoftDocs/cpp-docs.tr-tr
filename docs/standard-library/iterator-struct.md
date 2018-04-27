---
title: iterator yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- xutility/std::iterator
dev_langs:
- C++
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6bf766bdcb63ae4d50006f4a2d7722238663c610
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
