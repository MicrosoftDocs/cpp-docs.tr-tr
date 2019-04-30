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
ms.openlocfilehash: 3e2e62946325c082e761b6997ae584419175f8fe
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64346189"
---
# <a name="moveiterator-class"></a>move_iterator Sınıfı

Sınıf şablonu `move_iterator` bir yineleyici için bir sarmalayıcıdır. Move_iterator yineleyicinin onu sarmaladığıyla (depoladığı) aynı davranışı sağlar, yalnız bu öğe bir kopyayı taşıma durumuna çevirerek depolanan yineleyicinin başvuru kaldırma işlecini bir rvalue başvurusuna çevirir. Rvalues hakkında daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class move_iterator;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, başvuru kaldırılması dışında bir yineleyici gibi davranan bir nesneyi tanımlar. Türünün rastgele erişim yineleyicisini depolar `Iterator`üye işlevi yoluyla erişilebilen `base()`. Tüm işlemler bir `move_iterator` doğrudan depolanmış yineleyiciyi üzerinde gerçekleştirilen dışında sonucunu `operator*` için örtük dönüştürme `value_type&&` bir rvalue başvurusu yapmak.

A `move_iterator` Sarmalanan yineleyici tarafından tanımlanmayan işlemler özelliğine sahip olabilir. Bu işlemler kullanılmamalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[move_iterator](#move_iterator)|Türündeki nesneler için oluşturucu `move_iterator`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iterator_type](#iterator_type)|Şablon parametresi için bir eşanlamlı `RandomIterator`.|
|[iterator_category](#iterator_category)|Uzun ilişkin bir eşanlam **typename** aynı adlı ifade `iterator_category` yineleyicinin genel yeteneklerini tanımlar.|
|[value_type](#value_type)|Uzun ilişkin bir eşanlam **typename** aynı adlı ifade `value_type` ne yineleyici öğelerinin türünü tanımlar.|
|[difference_type](#difference_type)|Uzun ilişkin bir eşanlam **typename** aynı adlı ifade `difference_type` öğeler arasındaki fark değerlerini için gereken integral türünü tanımlar.|
|[İşaretçi](#pointer)|Şablon parametresi için bir eşanlamlı `RandomIterator`.|
|[Başvuru](#reference)|İçin bir eşanlamlı `rvalue` başvuru `value_type&&`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Üye işlevi bu tarafından Sarmalanan depolanmış yineleyiciyi döndürür `move_iterator`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[move_iterator::operator*](#op_star)|döndürür `(reference)*base().`|
|[move_iterator::operator++](#op_add_add)|Depolanmış yineleyiciyi artırır. Tam davranış artırma öncesi mi artırma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operator--](#operator--)|Depolanan yineleyiciyi azaltır. Tam davranış azaltma öncesi mi azaltma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operator-&gt;](#op_arrow)|Döndürür `&**this`.|
|[move_iterator::operator-](#operator-)|Döndürür `move_iterator(*this) -=` geçerli konumdaki sağ değeri ilk önce çıkararak çıkarma.|
|[move_iterator::operator[]](#op_at)|Döndürür `(reference)*(*this + off)`. Bu konumdaki değeri elde etmek için geçerli temel bir uzaklık belirtmenizi sağlar.|
|[move_iterator::operator+](#op_add)|Döndürür `move_iterator(*this) +=` değeri. Bu konumdaki değeri elde etmek için geçerli temele bir uzaklık eklemenizi sağlar.|
|[move_iterator::operator+=](#op_add_eq)|Sağdaki değerin saklı yineleyiciye ekler ve döndürür `*this`.|
|[move_iterator::operator-=](#operator-_eq)|Depolanmış yineleyiciyi sağ değeri çıkarır ve döndürür `*this`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yineleyici >

**Namespace:** std

## <a name="base"></a>  move_iterator::Base

Bunun için depolanmış yineleyiciyi döndürür `move_iterator`.

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi, depolanmış yineleyiciyi döndürür.

## <a name="difference_type"></a>  move_iterator::difference_type

Türü `difference_type` olduğu bir `move_iterator` `typedef` üzerinde yineleyici niteliğine göre `difference_type`ve onunla birbirlerinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyici nitelik eşanlamlıdır `typename iterator_traits<RandomIterator>::pointer`.

## <a name="iterator_category"></a>  move_iterator::iterator_category

Türü `iterator_category` olduğu bir `move_iterator` `typedef` üzerinde yineleyici niteliğine göre `iterator_category`ve onunla birbirlerinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyici nitelik eşanlamlıdır `typename iterator_traits<RandomIterator>::iterator_category`.

## <a name="iterator_type"></a>  move_iterator::iterator_type

Türü `iterator_type` şablon parametresini temel alan `RandomIterator` sınıf şablonunun `move_iterator`ve onun yerine birbirlerinin yerine kullanılabilir.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür `RandomIterator`.

## <a name="move_iterator"></a>  move_iterator::move_iterator

Bir taşıma yineleyicisi oluşturur. Parametre depolanmış yineleyiciyi kullanır.

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Depolanmış yineleyiciyi kullanmak için bir yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu depolanmış yineleyiciyi ile kendi varsayılan oluşturucusunu başlatır. Kalan oluşturucular ile depolanmış yineleyiciyi başlatmak `base.base()`.

## <a name="op_add_eq"></a>  move_iterator::operator +=

Depolanmış yineleyiciyi öğeye yeni geçerli konumda göstermeyecek şekilde depolanmış yineleyiciyi için bir uzaklık ekler. İşleci, ardından yeni geçerli öğe taşır.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*<br/>
Yeni geçerli konumunu belirlemek için geçerli konumun eklemek için bir uzaklık.

### <a name="return-value"></a>Dönüş Değeri

Yeni geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

İşleç ekler *_Off* depolanmış yineleyiciyi için. Ardından döndürür `*this`.

## <a name="operator-_eq"></a>  move_iterator::operator-=

Belirtilen sayıda önceki öğeler arasında taşır. Bu işleç, depolanmış yineleyiciyi bir uzaklık çıkarır.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleç değerlendirir `*this += -_Off`. Ardından döndürür `*this`.

## <a name="op_add_add"></a>  move_iterator::operator++

Şuna ait olan depolanmış yineleyiciyi artırır `move_iterator.` geçerli öğe postincrement işleci tarafından erişilir. Sonraki öğeye preincrement işleci tarafından erişilir.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk (artırma) işleci, depolanmış yineleyiciyi artırır. Ardından döndürür `*this`.

İkinci işleç (artırma sonrası) bir kopyasını oluşturur `*this`, değerlendirir `++*this`. Daha sonra kopyayı döndürür.

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

## <a name="operator--"></a>  move_iterator::operator--

Öncesi ve postdecrement üye işleçleri bir azaltma depolanmış yineleyiciyi üzerinde gerçekleştirin.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk üye işleci (azaltma) azaltır depolanmış yineleyiciyi. Ardından döndürür `*this`.

İkinci işleç (azaltma sonrası) bir kopyasını oluşturur `*this`, değerlendirir `--*this`. Daha sonra kopyayı döndürür.

## <a name="operator-"></a>  move_iterator::operator-

Azaltır depolanmış yineleyiciyi ve belirtilen değeri döndürür.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleç döndürür `move_iterator(*this) -= _Off`.

## <a name="op_star"></a>  move_iterator::operator*

Depolanmış yineleyiciyi başvurusunu kaldırır ve değeri döndürür. Bu gibi davranan bir `rvalue reference` ve taşıma ataması gerçekleştirir. İşleci, geçerli öğe temel yineleyicisi dışında aktarır. Yeni geçerli öğeyi izleyen öğe olur.

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

Türü `pointer` olduğu bir **typedef** üzerinde rastgele yineleyicinin tabanlı `RandomIterator` için `move_iterator`ve birbirlerinin yerine kullanılabilir.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `RandomIterator`.

## <a name="reference"></a>  move_iterator::Reference

Türü `reference` olduğu bir **typedef** göre `value_type&&` için `move_iterator`ve birbirlerinin yerine kullanılabilir `value_type&&`.

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü eşanlamlıdır `value_type&&`, bir rvalue başvurusu olduğu.

## <a name="value_type"></a>  move_iterator::value_type

Türü `value_type` olduğu bir `move_iterator` `typedef` üzerinde yineleyici niteliğine göre `value_type`ve onunla birbirlerinin yerine kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Açıklamalar

Türü yineleyici nitelik eşanlamlıdır `typename iterator_traits<RandomIterator>::value_type`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)<br/>
[Lvalue ve Rvalue’lar](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
[Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
