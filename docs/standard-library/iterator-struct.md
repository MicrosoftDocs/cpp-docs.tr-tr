---
title: iterator Yapısı
ms.date: 11/04/2016
f1_keywords:
- xutility/std::iterator
helpviewer_keywords:
- iterator class
- iterator struct
ms.assetid: c74c8000-8b18-4829-9b71-6103c4229b74
ms.openlocfilehash: 1dd62a6141e690d3bd4dcad69aa107c126a0f386
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62224109"
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
