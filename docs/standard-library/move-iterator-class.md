---
title: move_iterator Sınıfı
ms.date: 03/27/2019
f1_keywords:
- iterator/std::move_iterator
- iterator/std::move_iterator::iterator_type
- iterator/std::move_iterator::iterator_category
- iterator/std::move_iterator::value_type
- iterator/std::move_iterator::difference_type
- iterator/std::move_iterator::pointer
- iterator/std::move_iterator::reference
- iterator/std::move_iterator::base
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
ms.openlocfilehash: 17af246a85c4e3f1e0c7eb9d387161ad7b5123a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377416"
---
# <a name="move_iterator-class"></a>move_iterator Sınıfı

Sınıf `move_iterator` şablonu bir yineleyici için bir sarmalayıcıdır. Move_iterator yineleyicinin onu sarmaladığıyla (depoladığı) aynı davranışı sağlar, yalnız bu öğe bir kopyayı taşıma durumuna çevirerek depolanan yineleyicinin başvuru kaldırma işlecini bir rvalue başvurusuna çevirir. Rvalues hakkında daha fazla bilgi için [Bkz. Rvalue Başvuru Bildirimcisi: &&. ](../cpp/rvalue-reference-declarator-amp-amp.md)

## <a name="syntax"></a>Sözdizimi

```cpp
class move_iterator;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, başvurunun silinmediği durumlar dışında bir yineleyici gibi görünen bir nesneyi açıklar. Üye işlev `base()`le erişilen, rastgele `Iterator`erişilen bir tür yinelemedepolar. Bir `move_iterator` yinelemedeki tüm işlemler, bir `operator*` rvalue başvurusu yapmak için `value_type&&` dolaylı olarak atılması dışında, doğrudan depolanan yineleyici üzerinde gerçekleştirilir.

A, `move_iterator` sarılmış yineleyici tarafından tanımlanmayan işlemler yapabilir. Bu işlemler kullanılmamalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[move_iterator](#move_iterator)|Tür `move_iterator`nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iterator_type](#iterator_type)|Şablon parametresi `RandomIterator`için eşanlamlı.|
|[iterator_category](#iterator_category)|Aynı adı taşıyan daha uzun bir **yazı tipi** `iterator_category` ifadesinin eş anlamlısı, yineleyicinin genel yeteneklerini tanımlar.|
|[value_type](#value_type)|Aynı adı taşıyan daha uzun bir **yazı tipi** `value_type` ifadesinin eş anlamlısı, yineleyici öğelerinin türünü açıklar.|
|[difference_type](#difference_type)|Aynı adı taşıyan daha uzun bir **yazı adı** `difference_type` ifadesinin eş anlamlısı, öğeler arasındaki fark değerlerini ifade etmek için gereken integral türünü açıklar.|
|[pointer](#pointer)|Şablon parametresi `RandomIterator`ile eş anlamlıdır.|
|[Başvuru](#reference)|Başvuruiçin `value_type&&`eş anlamlı. `rvalue`|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[base](#base)|Üye işlev, depolanan yinelemeyi bu `move_iterator`tarafından sarılmış olarak döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[move_iterator::operatör*](#op_star)|Döndürür`(reference)*base().`|
|[move_iterator::operator++](#op_add_add)|Depolanmış yineleyiciyi artırır. Tam davranış artırma öncesi mi artırma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operatör--](#operator--)|Depolanan yineleyiciyi azaltır. Tam davranış azaltma öncesi mi azaltma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operatör-&gt;](#op_arrow)|`&**this` döndürür.|
|[move_iterator::operatör-](#operator-)|İlk `move_iterator(*this) -=` olarak sağ daki değeri geçerli konumdan çıkararak döndürür.|
|[move_iterator::operatör[]](#op_at)|`(reference)*(*this + off)` döndürür. Bu konumdaki değeri elde etmek için geçerli temel bir uzaklık belirtmenizi sağlar.|
|[move_iterator::operatör+](#op_add)|Değeri `move_iterator(*this) +=` verir. Bu konumdaki değeri elde etmek için geçerli temele bir uzaklık eklemenizi sağlar.|
|[move_iterator::operator+=](#op_add_eq)|Depolanan yineleyiciye sağ değer ekler ve döndürür. `*this`|
|[move_iterator::operator-=](#operator-_eq)|Depolanan yineleyiciden sağ el değerini çıkarır ve döndürür. `*this`|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yineleyici>

**Ad alanı:** std

## <a name="move_iteratorbase"></a><a name="base"></a>move_iterator::taban

Bunun için depolanan yineleyiciyi `move_iterator`döndürür.

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlev depolanan yineleyiciyi döndürür.

## <a name="move_iteratordifference_type"></a><a name="difference_type"></a>move_iterator::difference_type

Türü `difference_type` yineleyici `move_iterator` `typedef` özelliğine dayalı bir `difference_type`, ve onunla birbirinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür yineleyici özelliği için `typename iterator_traits<RandomIterator>::pointer`eşanlamlıdır.

## <a name="move_iteratoriterator_category"></a><a name="iterator_category"></a>move_iterator::iterator_category

Türü `iterator_category` yineleyici `move_iterator` `typedef` özelliğine dayalı bir `iterator_category`, ve onunla birbirinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür yineleyici özelliği için `typename iterator_traits<RandomIterator>::iterator_category`eşanlamlıdır.

## <a name="move_iteratoriterator_type"></a><a name="iterator_type"></a>move_iterator:iterator_type

Tür, `iterator_type` sınıf şablonu `RandomIterator` `move_iterator`için şablon parametresini temel alıntır ve yerine birbirinin yerine kullanılabilir.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `RandomIterator`ile eş anlamlıdır.

## <a name="move_iteratormove_iterator"></a><a name="move_iterator"></a>move_iterator:move_iterator

Hareket yineleyicisi inşa eder. Depolanan yineleyici olarak parametrekullanır.

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Depolanan yineleyici olarak kullanılacak yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, varsayılan oluşturucusuyla depolanan yineleyiciyi başharfe alır. Kalan oluşturucular depolanan yineleyiciyi `base.base()`.

## <a name="move_iteratoroperator"></a><a name="op_add_eq"></a>move_iterator::operator+=

Depolanan yineleyiciye bir ofset ekler, böylece depolanan yineleyici yeni geçerli konumdaki öğeyi işaret edin. İşleç daha sonra yeni geçerli öğeyi taşır.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_off*\
Yeni geçerli konumu belirlemek için geçerli konuma eklemek için bir ofset.

### <a name="return-value"></a>Dönüş Değeri

Yeni geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Operatör depolanan yineleyiciye *_Off* ekler. Sonra `*this`döner.

## <a name="move_iteratoroperator-"></a><a name="operator-_eq"></a>move_iterator::operator-=

Önceki öğelerin belirli bir sayıda arasında taşır. Bu işleç depolanan yineleyiciden bir ofset çıkarır.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

Operatör `*this += -_Off`değerlendirir. Sonra `*this`döner.

## <a name="move_iteratoroperator"></a><a name="op_add_add"></a>move_iterator::operator++

Bu `move_iterator.` hesaba ait depolanan yinelemeyi artışlar Geçerli öğeye postincrement işleci tarafından erişilir. Bir sonraki öğeye preincrement işleci tarafından erişilir.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk (preincrement) işleci depolanan yineleyiciyi hızlandırıyor. Sonra `*this`döner.

İkinci (postincrement) işleci bir `*this`kopyasını `++*this`yapar , değerlendirir. Sonra kopyayı döndürür.

## <a name="move_iteratoroperator"></a><a name="op_add"></a>move_iterator::operatör+

Herhangi bir sayıda öğe tarafından gelişmiş yineleyici konumunu döndürür.

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

Operatör döndürür. `move_iterator(*this) +=` `_Off`

## <a name="move_iteratoroperator"></a><a name="op_at"></a>move_iterator::operatör[]

Dizi dizinin aralığındaki öğelere `move iterator`erişmesine izin verir.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

Operatör döndürür. `(reference)*(*this + _Off)`

## <a name="move_iteratoroperator--"></a><a name="operator--"></a>move_iterator::operatör--

Ön ve posta üye operatörleri depolanan yineleyici üzerinde bir kararname gerçekleştirir.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk üye işleç (predecrement) depolanan yineleyiciyi kararnameye atar. Sonra `*this`döner.

İkinci (postdecrement) işleci bir `*this`kopyasını `--*this`yapar , değerlendirir. Sonra kopyayı döndürür.

## <a name="move_iteratoroperator-"></a><a name="operator-"></a>move_iterator::operatör-

Depolanan yineleyiciyi verir ve belirtilen değeri döndürür.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

Operatör döndürür. `move_iterator(*this) -= _Off`

## <a name="move_iteratoroperator"></a><a name="op_star"></a>move_iterator::operatör*

Depolanan yineleyiciyi dereferences ve değeri döndürür. Bu bir `rvalue reference` gibi hareket eder ve bir taşıma ataması gerçekleştirir. İşleç, geçerli öğeyi temel yineleyiciden dışarı yatarım. İzleyen öğe yeni geçerli öğe olur.

```cpp
reference operator*() const;
```

### <a name="remarks"></a>Açıklamalar

Operatör döndürür. `(reference)*base()`

## <a name="move_iteratoroperator-gt"></a><a name="op_arrow"></a>move_iterator::operatör-&gt;

Normal `RandomIterator` `operator->`bir öğe gibi, geçerli öğeye ait alanlara erişim sağlar.

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>Açıklamalar

Operatör döndürür. `&**this`

## <a name="move_iteratorpointer"></a><a name="pointer"></a>move_iterator::pointer

Türü `pointer` için `RandomIterator` `move_iterator`rasgele yineleyici dayalı bir **typedef** , ve birbirlerinin yerine kullanılabilir.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü için `RandomIterator`eşanlamlıdır.

## <a name="move_iteratorreference"></a><a name="reference"></a>move_iterator::başvuru

Türü `reference` için `move_iterator`dayalı `value_type&&` `value_type&&` bir **typedef** , ve birbirinin yerine kullanılabilir .

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Açıklamalar

`value_type&&`Tür, rvalue başvurusu olan eşanlamlıdır.

## <a name="move_iteratorvalue_type"></a><a name="value_type"></a>move_iterator::value_type

Türü `value_type` yineleyici `move_iterator` `typedef` özelliğine dayalı bir `value_type`, ve onunla birbirinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür yineleyici özelliği için `typename iterator_traits<RandomIterator>::value_type`eşanlamlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)\
[Yapı oluşturucuları ve Taşıma Atama Operatörlerini Taşı (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)\
[C++ Standart Kütüphane Başvurusu](../standard-library/cpp-standard-library-reference.md)
