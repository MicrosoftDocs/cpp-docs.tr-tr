---
title: move_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- iterator/std::move_iterator
- iterator/std::move_iterator::iterator_type
- iterator/std::move_iterator::iterator_category
- iterator/std::move_iterator::value_type
- iterator/std::move_iterator::difference_type
- iterator/std::move_iterator::pointer
- iterator/std::move_iterator::reference
- iterator/std::move_iterator::base
dev_langs:
- C++
helpviewer_keywords:
- std::move_iterator [C++]
- std::move_iterator [C++], iterator_type
- std::move_iterator [C++], iterator_category
- std::move_iterator [C++], value_type
- std::move_iterator [C++], difference_type
- std::move_iterator [C++], pointer
- std::move_iterator [C++], reference
- std::move_iterator [C++], base
ms.assetid: a5e5cdd8-a264-4c6b-9f9c-68b0e8edaab7
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 519da720c3dcab278a21e04baa97d1eb6e459054
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="moveiterator-class"></a>move_iterator Sınıfı

Sınıf şablonu `move_iterator` yineleyici için sarmalayıcı değil. Move_iterator yineleyicinin onu sarmaladığıyla (depoladığı) aynı davranışı sağlar, yalnız bu öğe bir kopyayı taşıma durumuna çevirerek depolanan yineleyicinin başvuru kaldırma işlecini bir rvalue başvurusuna çevirir. Rvalues hakkında daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class move_iterator;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, başvuru kaldırılması dışında bir yineleyici gibi davranan bir nesneyi tanımlar. Rasgele erişim yineleyici türü depolar `Iterator`, üye fonksiyonu aracılığıyla erişilen `base()`. Tüm işlemler bir `move_iterator` doğrudan saklı yineleyici üzerinde gerçekleştirilen dışında sonucu `operator*` için örtük olarak cast `value_type&&` rvalue başvuru yapma.

A `move_iterator` tarafından Sarmalanan yineleyici tanımlı değil işlemlerinin yeteneğine sahip olabilir. Bu işlemler kullanılmamalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[move_iterator](#move_iterator)|Nesne türü Oluşturucusu `move_iterator`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iterator_type](#iterator_type)|Şablon parametresi için bir eş anlamlı `RandomIterator`.|
|[iterator_category](#iterator_category)|Bir uzun bir eş anlamlı `typename` ifadesi aynı ada sahip `iterator_category` yineleyici genel yeteneklerini tanımlar.|
|[value_type](#value_type)|Bir eş anlamlı daha uzun bir süre `typename` ifadesi aynı ada sahip `value_type` öğeler yineleyici ne tür açıklar.|
|[difference_type](#difference_type)|Bir uzun bir eş anlamlı `typename` ifadesi aynı ada sahip `difference_type` öğeler arasında hızlı fark değerleri için gerekli olan tam sayı türü açıklanmaktadır.|
|[İşaretçi](#pointer)|Şablon parametresi için bir eş anlamlı `RandomIterator`.|
|[Başvuru](#reference)|Eşanlamlısı `rvalue` başvuru `value_type&&`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Üye işlevi bu tarafından Sarmalanan saklı yineleyici döndürür `move_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[move_iterator::operator*](#op_star)|döndürür `(reference)*base().`|
|[move_iterator::operator++](#op_add_add)|Depolanmış yineleyiciyi artırır. Tam davranış artırma öncesi mi artırma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operator--](#operator--)|Depolanan yineleyiciyi azaltır. Tam davranış azaltma öncesi mi azaltma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operator-&gt;](#op_arrow)|Döndürür `&**this`.|
|[move_iterator::operator-](#operator-)|Döndürür `move_iterator(*this) -=` geçerli konumdan sağ değeri tarafından ilk çıkararak.|
|[move_iterator::operator[]](#op_at)|Döndürür `(reference)*(*this + off)`. Bu konumdaki değeri elde etmek için geçerli temel bir uzaklık belirtmenizi sağlar.|
|[move_iterator::operator+](#op_add)|Döndürür `move_iterator(*this) +=` değeri. Bu konumdaki değeri elde etmek için geçerli temele bir uzaklık eklemenizi sağlar.|
|[move_iterator::operator+=](#op_add_eq)|Sağ taraftaki değeri saklı yineleyici ekler ve döndürür `*this`.|
|[move_iterator::operator-=](#operator-_eq)|Saklı yineleyici sağ değerinden çıkarır ve döndürür `*this`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="base"></a>  move_iterator::Base

Bu saklı yineleyici döndürür `move_iterator`.

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevini saklı yineleyici döndürür.

## <a name="difference_type"></a>  move_iterator::difference_type

Türü `difference_type` olan bir `move_iterator` `typedef` yineleyici ayırdedici nitelik üzerinde temel `difference_type`ve onunla birbirinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Yineleyici ayırdedici nitelik eşanlamlısı türüdür `typename iterator_traits<RandomIterator>::pointer`.

## <a name="iterator_category"></a>  move_iterator::iterator_category

Türü `iterator_category` olan bir `move_iterator` `typedef` yineleyici ayırdedici nitelik üzerinde temel `iterator_category`ve onunla birbirinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Yineleyici ayırdedici nitelik eşanlamlısı türüdür `typename iterator_traits<RandomIterator>::iterator_category`.

## <a name="iterator_type"></a>  move_iterator::iterator_type

Türü `iterator_type` şablon parametresi temelinde `RandomIterator` sınıfı şablonu için `move_iterator`ve onun yerine birbirinin yerine kullanılabilir.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür `RandomIterator`.

## <a name="move_iterator"></a>  move_iterator::move_iterator

Bir taşıma yineleyici oluşturur. Parametre depolanan yineleyici kullanır.

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

`right` Saklı yineleyici kullanılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu saklı yineleyici kendi varsayılan oluşturucu ile başlatır. Kalan oluşturucular ile saklı yineleyici başlatma `base.base()`.

## <a name="op_add_eq"></a>  move_iterator::operator +=

Saklı yineleyici yeni geçerli konumda öğesine işaret eden bir uzaklık saklı yineleyici için ekler. İşleci, ardından yeni bir geçerli öğesi taşır.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

`_Off` Yeni geçerli konumunu belirlemek için geçerli konumu eklemek için bir uzaklık.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir geçerli öğesi döndürür.

### <a name="remarks"></a>Açıklamalar

İşleç ekler `_Off` saklı yineleyici için. ardından döndürür `*this`.

## <a name="move_iterator__operator-_eq"></a>  move_iterator::operator-=

Belirtilen sayıda önceki öğeyi arasında taşır. Bu işleç saklı yineleyici uzaklık çıkarır.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleç değerlendirir `*this += -_Off`. ardından döndürür `*this`.

## <a name="op_add_add"></a>  move_iterator::operator++

Bunun için ait olduğu saklı yineleyici artırır `move_iterator.` geçerli öğe postincrement operatör tarafından erişilir. Sonraki öğeye preincrement operatör tarafından erişilir.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk (preincrement) işleci saklı yineleyici artırır. ardından döndürür `*this`.

İkinci (postincrement) işleci bir kopyasını oluşturur `*this`, hesaplar `++*this`. Ardından kopya döndürür.

## <a name="op_add"></a>  move_iterator::operator+

Herhangi bir sayıda öğe Gelişmiş yineleyici konumunu döndürür.

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleç döndürür `move_iterator(*this) +=` `_Off`.

## <a name="op_at"></a>  move_iterator::operator]

Dizi dizini öğeleri aralığı erişime izin `move iterator`.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleç döndürür `(reference)*(*this + _Off)`.

## <a name="move_iterator__operator--"></a>  move_iterator::operator--

Ön ve postdecrement üye işleçleri bir azaltma saklı yineleyici üzerinde gerçekleştirin.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk üye işleci (predecrement) azaltır saklı yineleyici. ardından döndürür `*this`.

İkinci (postdecrement) işleci bir kopyasını oluşturur `*this`, hesaplar `--*this`. Ardından kopya döndürür.

## <a name="move_iterator__operator-"></a>  move_iterator::operator-

Azaltır saklı Yineleyici ve belirtilen değeri döndürür.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleç döndürür `move_iterator(*this) -= _Off`.

## <a name="op_star"></a>  move_iterator::operator*

Saklı yineleyici dereferences ve değeri döndürür. Bu gibi davranır bir `rvalue reference` ve taşıma atama gerçekleştirir. İşleç geçerli öğe temel yineleyici dışında aktarır. Aşağıdaki öğe yeni geçerli öğe haline gelir.

```cpp
reference operator*() const;
```

### <a name="remarks"></a>Açıklamalar

İşleç döndürür `(reference)*base()`.

## <a name="op_arrow"></a>  move_iterator::operator-&gt;

Gibi normal `RandomIterator` `operator->`, geçerli öğeye ait alanlarına erişim sağlar.

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>Açıklamalar

İşleç döndürür `&**this`.

## <a name="pointer"></a>  move_iterator::pointer

Türü `pointer` olan bir `typedef` rastgele yineleyici üzerinde temel `RandomIterator` için `move_iterator`ve birbirlerinin yerine kullanılabilir.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `RandomIterator`.

## <a name="reference"></a>  move_iterator::Reference

Türü `reference` olan bir `typedef` göre `value_type&&` için `move_iterator`ve birbirlerinin yerine kullanılabilir `value_type&&`.

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Açıklamalar

Eşanlamlısı türüdür `value_type&&`, rvalue başvuru olduğu.

## <a name="value_type"></a>  move_iterator::value_type

Türü `value_type` olan bir `move_iterator` `typedef` yineleyici ayırdedici nitelik üzerinde temel `value_type`ve onunla birbirinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Açıklamalar

Yineleyici ayırdedici nitelik eşanlamlısı türüdür `typename iterator_traits<RandomIterator>::value_type`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
[Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
