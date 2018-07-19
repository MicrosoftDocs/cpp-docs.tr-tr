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
ms.openlocfilehash: a399fa8a9f8fc9a73d75605f31245e42a2154b7c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38963634"
---
# <a name="iterator-struct"></a>iterator Yapısı

Bir kullanıcı tanımlı iterator sınıfı düzgün ile çalıştığından emin olmak için kullanılan boş bir temel yapı `iterator_trait`s.

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

Şablon yapı tüm yineleyiciler için bir temel tür olarak görev yapar. Üye türleri tanımlar

- `iterator_category` (şablon parametresi için bir eşanlamlı `Category`).

- `value_type` (şablon parametresi için bir eşanlamlı `Type`).

- `difference_type` (şablon parametresi için bir eşanlamlı `Distance`).

- `distance_type` (şablon parametresi için bir eşanlamlı `Distance`)

- `pointer` (şablon parametresi için bir eşanlamlı `Pointer`).

- `reference` (şablon parametresi için bir eşanlamlı `Reference`).

Unutmayın `value_type` sabit türü bile olmamalıdır `pointer` nesnenin noktalarda **const** `Type` ve başvurusu bir nesnenin atar **const** `Type`.

## <a name="example"></a>Örnek

Bkz: [iterator_traits](../standard-library/iterator-traits-struct.md) bildirmek ve yineleyici temel sınıf türleri kullanma örneği için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
