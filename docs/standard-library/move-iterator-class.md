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
ms.openlocfilehash: 55e0c23aaf085a132ecab739ec1d4ff1f11858a0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228199"
---
# <a name="move_iterator-class"></a>move_iterator Sınıfı

Sınıf şablonu `move_iterator` , Yineleyici için bir sarmalayıcıdır. Move_iterator yineleyicinin onu sarmaladığıyla (depoladığı) aynı davranışı sağlar, yalnız bu öğe bir kopyayı taşıma durumuna çevirerek depolanan yineleyicinin başvuru kaldırma işlecini bir rvalue başvurusuna çevirir. Rvalues hakkında daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class move_iterator;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, başvurunun başvurulması dışında bir yineleyici gibi davranan bir nesneyi tanımlar. Üye işlevi yoluyla erişilen türünde, Rastgele erişimli bir yineleyici depolar `Iterator` `base()` . İçindeki tüm işlemler `move_iterator` doğrudan depolanan yineleyiciden gerçekleştirilir, ancak sonucu bir `operator*` `value_type&&` rvalue başvurusu yapmak için örtük olarak ' a dönüştürülür.

Bir bir `move_iterator` , Sarmalanan Yineleyici tarafından tanımlanmayan işlemler yeteneğine sahip olabilir. Bu işlemler kullanılmamalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[move_iterator](#move_iterator)|Türündeki nesneler için Oluşturucu `move_iterator` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iterator_type](#iterator_type)|Şablon parametresi için bir eş anlamlı `RandomIterator` .|
|[iterator_category](#iterator_category)|Aynı ada sahip daha uzun bir ifadenin eşanlamlısı **`typename`** , `iterator_category` yineleyicinin genel yeteneklerini tanımlar.|
|[value_type](#value_type)|Aynı ada sahip daha uzun bir ifadenin eşanlamlısı **`typename`** , `value_type` Yineleyici öğelerinin ne tür olduğunu açıklar.|
|[difference_type](#difference_type)|Aynı ada sahip daha uzun bir ifadenin eşanlamlısı **`typename`** , `difference_type` öğeler arasındaki fark değerlerini ifade etmek için gereken integral türünü açıklar.|
|[pointer](#pointer)|Şablon parametresi için eş anlamlı `RandomIterator` .|
|[başvurunun](#reference)|Başvuru için bir eş `rvalue` anlamlı `value_type&&` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Üye işlevi, bu tarafından Sarmalanan saklı yineleyiciyi döndürür `move_iterator` .|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[move_iterator:: operator *](#op_star)|Döndürdüğü`(reference)*base().`|
|[move_iterator:: operator + +](#op_add_add)|Depolanmış yineleyiciyi artırır. Tam davranış artırma öncesi mi artırma sonrası mı olduğuna bağlıdır.|
|[move_iterator:: operator--](#operator--)|Depolanan yineleyiciyi azaltır. Tam davranış azaltma öncesi mi azaltma sonrası mı olduğuna bağlıdır.|
|[move_iterator:: operator-&gt;](#op_arrow)|`&**this` döndürür.|
|[move_iterator:: operator-](#operator-)|`move_iterator(*this) -=`İlk olarak geçerli konumdan doğru değeri çıkararak döndürür.|
|[move_iterator:: operator []](#op_at)|`(reference)*(*this + off)` döndürür. Bu konumdaki değeri elde etmek için geçerli temel bir uzaklık belirtmenizi sağlar.|
|[move_iterator:: operator +](#op_add)|`move_iterator(*this) +=`Değeri döndürür. Bu konumdaki değeri elde etmek için geçerli temele bir uzaklık eklemenizi sağlar.|
|[move_iterator:: operator + =](#op_add_eq)|Depolanan yineleyiciye sağ değeri ekler ve döndürür **`*this`** .|
|[move_iterator:: operator-=](#operator-_eq)|Depolanan yineleyiciden sağ değeri çıkartır ve döndürür **`*this`** .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<iterator>

**Ad alanı:** std

## <a name="move_iteratorbase"></a><a name="base"></a>move_iterator:: Base

Bu için depolanan yineleyiciyi döndürür `move_iterator` .

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi depolanan yineleyiciyi döndürür.

## <a name="move_iteratordifference_type"></a><a name="difference_type"></a>move_iterator::d ifference_type

Tür, `difference_type` `move_iterator` **`typedef`** Yineleyici nitelik temel alınarak `difference_type` kullanılabilir ve bunun yerine onunla birlikte kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik için bir eş anlamlı `typename iterator_traits<RandomIterator>::pointer` .

## <a name="move_iteratoriterator_category"></a><a name="iterator_category"></a>move_iterator:: iterator_category

Tür, `iterator_category` `move_iterator` **`typedef`** Yineleyici nitelik temel alınarak `iterator_category` kullanılabilir ve bunun yerine onunla birlikte kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik için bir eş anlamlı `typename iterator_traits<RandomIterator>::iterator_category` .

## <a name="move_iteratoriterator_type"></a><a name="iterator_type"></a>move_iterator:: iterator_type

Türü, `iterator_type` sınıf şablonu için Şablon parametresine dayalıdır `RandomIterator` `move_iterator` ve yerine birbirinin yerine kullanılabilir.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi için bir eş anlamlı `RandomIterator` .

## <a name="move_iteratormove_iterator"></a><a name="move_iterator"></a>move_iterator:: move_iterator

Taşıma yineleyicisi oluşturur. , Parametresini saklı Yineleyici olarak kullanır.

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Saklı Yineleyici olarak kullanılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, saklı yineleyiciyi varsayılan Oluşturucusu ile başlatır. Kalan oluşturucular, depolanan yineleyiciyi ile başlatır `base.base()` .

## <a name="move_iteratoroperator"></a><a name="op_add_eq"></a>move_iterator:: operator + =

Depolanan yineleyici için bir konum ekler ve bu sayede saklı Yineleyici yeni geçerli konumdaki öğeyi işaret eder. İşleci ardından yeni geçerli öğeyi taşıtir.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Off*\
Yeni geçerli konumu belirlemekte geçerli konuma eklenecek bir konum.

### <a name="return-value"></a>Dönüş Değeri

Yeni geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

İşleci, depolanan yineleyiciye *_Off* ekler. Ardından döndürür **`*this`** .

## <a name="move_iteratoroperator-"></a><a name="operator-_eq"></a>move_iterator:: operator-=

Belirtilen sayıda önceki öğenin arasında gider. Bu işleç, depolanan yineleyiciden bir sapmayı çıkartır.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci değerlendirilir `*this += -_Off` . Ardından döndürür **`*this`** .

## <a name="move_iteratoroperator"></a><a name="op_add_add"></a>move_iterator:: operator + +

Geçerli öğeye ait saklı yineleyiciyi, `move_iterator.` postıncrement işleci tarafından erişilir. Next öğesine preıncrement işleci tarafından erişilir.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

Birincisi (preıncrement) işleci saklı yineleyiciyi arttırır. Ardından döndürür **`*this`** .

İkinci (postıncrement) işleci bir kopyası yapar **`*this`** , değerlendirir `++*this` . Sonra kopyayı döndürür.

## <a name="move_iteratoroperator"></a><a name="op_add"></a>move_iterator:: operator +

Yineleyici konumunu herhangi bir sayıda öğe tarafından gelişmiş döndürür.

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `move_iterator(*this) +=` `_Off` .

## <a name="move_iteratoroperator"></a><a name="op_at"></a>move_iterator:: operator []

Dizi dizininin öğe aralığı genelinde öğelere erişimine izin verir `move iterator` .

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `(reference)*(*this + _Off)` .

## <a name="move_iteratoroperator--"></a><a name="operator--"></a>move_iterator:: operator--

Ön ve geri azaltma üye işleçleri, saklı Yineleyici üzerinde bir azaltma gerçekleştirir.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk üye işleci (predecrement) depolanan yineleyiciyi azaltır. Ardından döndürür **`*this`** .

İkinci (postazaltma) işleci bir kopyası yapar **`*this`** , değerlendirir `--*this` . Sonra kopyayı döndürür.

## <a name="move_iteratoroperator-"></a><a name="operator-"></a>move_iterator:: operator-

Depolanan yineleyiciyi azaltır ve belirtilen değeri döndürür.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `move_iterator(*this) -= _Off` .

## <a name="move_iteratoroperator"></a><a name="op_star"></a>move_iterator:: operator *

Saklı yineleyiciden başvurur ve değeri döndürür. Bu, bir gibi davranır `rvalue reference` ve bir taşıma ataması gerçekleştirir. İşleci, geçerli öğeyi temel yineleyiciden aktarır. Aşağıdaki öğesi, yeni geçerli öğe haline gelir.

```cpp
reference operator*() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `(reference)*base()` .

## <a name="move_iteratoroperator-gt"></a><a name="op_arrow"></a>move_iterator:: operator-&gt;

Normal bir şekilde `RandomIterator` `operator->` , geçerli öğeye ait alanlara erişim sağlar.

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `&**this` .

## <a name="move_iteratorpointer"></a><a name="pointer"></a>move_iterator::p oınter

Türü `pointer` **`typedef`** , için rastgele Yineleyici temelinde `RandomIterator` `move_iterator` ve birbirinin yerine kullanılabilir.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür için bir eş anlamlı `RandomIterator` .

## <a name="move_iteratorreference"></a><a name="reference"></a>move_iterator:: Reference

Türü `reference` **`typedef`** , için temel bir tabanlıdır `value_type&&` `move_iterator` ve ile birbirlerinin yerine kullanılabilir `value_type&&` .

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir rvalue başvurusu olan için bir eş anladır `value_type&&` .

## <a name="move_iteratorvalue_type"></a><a name="value_type"></a>move_iterator:: value_type

Tür, `value_type` `move_iterator` **`typedef`** Yineleyici nitelik temel alınarak `value_type` kullanılabilir ve bunun yerine onunla birlikte kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik için bir eş anlamlı `typename iterator_traits<RandomIterator>::value_type` .

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator>](../standard-library/iterator.md)\
[Lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)\
[Taşıma Oluşturucuları ve taşıma atama Işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
