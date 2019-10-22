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
ms.openlocfilehash: 9e8334db52e05f4a61adb7256e87ed611f0d3ecb
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689276"
---
# <a name="move_iterator-class"></a>move_iterator Sınıfı

Sınıf şablonu `move_iterator` Yineleyici için bir sarmalayıcıdır. Move_iterator yineleyicinin onu sarmaladığıyla (depoladığı) aynı davranışı sağlar, yalnız bu öğe bir kopyayı taşıma durumuna çevirerek depolanan yineleyicinin başvuru kaldırma işlecini bir rvalue başvurusuna çevirir. Rvalues hakkında daha fazla bilgi için bkz. [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class move_iterator;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, başvurunun başvurulması dışında bir yineleyici gibi davranan bir nesneyi tanımlar. Üye işlevi `base()` tarafından erişilen `Iterator` türünde bir rastgele erişim yineleyicisini depolar. Bir `move_iterator` tüm işlemler doğrudan depolanan yineleyiciden yapılır, ancak `operator*` sonucu bir rvalue başvurusu yapmak için örtük olarak `value_type&&` olarak dönüştürülür.

@No__t_0, sarmalanmış Yineleyici tarafından tanımlanmayan işlemlere sahip olabilir. Bu işlemler kullanılmamalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[move_iterator](#move_iterator)|@No__t_0 türündeki nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iterator_type](#iterator_type)|Şablon parametresi için bir eş anlamlı `RandomIterator`.|
|[iterator_category](#iterator_category)|Aynı adın daha uzun **TypeName** ifadesi için bir eş anlamlı, `iterator_category` yineleyicinin genel yeteneklerini tanımlar.|
|[value_type](#value_type)|Aynı adın daha uzun **TypeName** ifadesi için bir eş anlamlı, `value_type` Yineleyici öğelerinin ne tür olduğunu açıklar.|
|[difference_type](#difference_type)|Aynı adın daha uzun **TypeName** ifadesi için bir eş anlamlı, `difference_type` öğeler arasındaki fark değerlerini ifade etmek için gereken integral türünü açıklar.|
|[çağrısı](#pointer)|Şablon parametresi için bir eş anlamlı `RandomIterator`.|
|[başvurunun](#reference)|@No__t_0 başvuru `value_type&&` için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Üye işlevi, bu `move_iterator` Sarmalanan saklı yineleyiciyi döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[move_iterator:: operator *](#op_star)|@No__t_0 döndürür|
|[move_iterator:: operator + +](#op_add_add)|Depolanmış yineleyiciyi artırır. Tam davranış artırma öncesi mi artırma sonrası mı olduğuna bağlıdır.|
|[move_iterator:: operator--](#operator--)|Depolanan yineleyiciyi azaltır. Tam davranış azaltma öncesi mi azaltma sonrası mı olduğuna bağlıdır.|
|[move_iterator:: operator-&gt;](#op_arrow)|@No__t_0 döndürür.|
|[move_iterator:: operator-](#operator-)|Geçerli konumdaki sağ değeri ilk çıkararak `move_iterator(*this) -=` döndürür.|
|[move_iterator:: operator []](#op_at)|@No__t_0 döndürür. Bu konumdaki değeri elde etmek için geçerli temel bir uzaklık belirtmenizi sağlar.|
|[move_iterator:: operator +](#op_add)|Değer `move_iterator(*this) +=` döndürür. Bu konumdaki değeri elde etmek için geçerli temele bir uzaklık eklemenizi sağlar.|
|[move_iterator:: operator + =](#op_add_eq)|Depolanan yineleyiciye sağ değeri ekler ve `*this` döndürür.|
|[move_iterator:: operator-=](#operator-_eq)|Depolanan yineleyiciden sağ değeri çıkartır ve `*this` döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<iterator >

**Ad alanı:** std

## <a name="base"></a>move_iterator:: Base

Bu `move_iterator` için depolanan yineleyiciyi döndürür.

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi depolanan yineleyiciyi döndürür.

## <a name="difference_type"></a>move_iterator::d ifference_type

Tür `difference_type`, yineleyici nitelik `difference_type` temel alınarak bir `move_iterator` `typedef` ve bunun yerine onunla birlikte kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik `typename iterator_traits<RandomIterator>::pointer` için bir eş anlamlı.

## <a name="iterator_category"></a>move_iterator::iterator_category

Tür `iterator_category`, yineleyici nitelik `iterator_category` temel alınarak bir `move_iterator` `typedef` ve bunun yerine onunla birlikte kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik `typename iterator_traits<RandomIterator>::iterator_category` için bir eş anlamlı.

## <a name="iterator_type"></a>move_iterator::iterator_type

Tür `iterator_type`, sınıf şablonu `move_iterator` için `RandomIterator` Şablon parametresine dayalıdır ve onun yerine birbirinin yerine kullanılabilir.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, `RandomIterator` şablon parametresi için bir eş anlamlı.

## <a name="move_iterator"></a>move_iterator::move_iterator

Taşıma yineleyicisi oluşturur. , Parametresini saklı Yineleyici olarak kullanır.

```cpp
move_iterator();
explicit move_iterator(RandomIterator right);
template <class Type>
move_iterator(const move_iterator<Type>& right);
```

### <a name="parameters"></a>Parametreler

*sağ* \
Saklı Yineleyici olarak kullanılacak Yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, saklı yineleyiciyi varsayılan Oluşturucusu ile başlatır. Kalan oluşturucular, depolanan yineleyiciyi `base.base()` ile başlatır.

## <a name="op_add_eq"></a>move_iterator:: operator + =

Depolanan yineleyici için bir konum ekler ve bu sayede saklı Yineleyici yeni geçerli konumdaki öğeyi işaret eder. İşleci ardından yeni geçerli öğeyi taşıtir.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Kapatma* \
Yeni geçerli konumu belirlemekte geçerli konuma eklenecek bir konum.

### <a name="return-value"></a>Dönüş Değeri

Yeni geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

İşleci, saklı Yineleyici için *_Kapalı* ekler. Sonra `*this` döndürür.

## <a name="operator-_eq"></a>move_iterator:: operator-=

Belirtilen sayıda önceki öğenin arasında gider. Bu işleç, depolanan yineleyiciden bir sapmayı çıkartır.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci `*this += -_Off` değerlendirir. Sonra `*this` döndürür.

## <a name="op_add_add"></a>move_iterator:: operator + +

Geçerli öğeye postıncrement işlecinin eriştiği bu `move_iterator.` ait saklı yineleyiciyi artırır. Next öğesine preıncrement işleci tarafından erişilir.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

Birincisi (preıncrement) işleci saklı yineleyiciyi arttırır. Sonra `*this` döndürür.

İkinci (postıncrement) işleci `*this` bir kopyasını yapar `++*this` değerlendirir. Sonra kopyayı döndürür.

## <a name="op_add"></a>move_iterator:: operator +

Yineleyici konumunu herhangi bir sayıda öğe tarafından gelişmiş döndürür.

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci `move_iterator(*this) +=` `_Off` döndürür.

## <a name="op_at"></a>move_iterator:: operator []

@No__t_0 aralığı genelinde öğelere dizi dizini erişimine izin verir.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci `(reference)*(*this + _Off)` döndürür.

## <a name="operator--"></a>move_iterator:: operator--

Ön ve geri azaltma üye işleçleri, saklı Yineleyici üzerinde bir azaltma gerçekleştirir.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk üye işleci (predecrement) depolanan yineleyiciyi azaltır. Sonra `*this` döndürür.

İkinci (postazaltma) işleci `*this` bir kopyasını yapar `--*this` değerlendirir. Sonra kopyayı döndürür.

## <a name="operator-"></a>move_iterator:: operator-

Depolanan yineleyiciyi azaltır ve belirtilen değeri döndürür.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci `move_iterator(*this) -= _Off` döndürür.

## <a name="op_star"></a>move_iterator:: operator *

Saklı yineleyiciden başvurur ve değeri döndürür. Bu bir `rvalue reference` gibi davranır ve bir taşıma ataması gerçekleştirir. İşleci, geçerli öğeyi temel yineleyiciden aktarır. Aşağıdaki öğesi, yeni geçerli öğe haline gelir.

```cpp
reference operator*() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci `(reference)*base()` döndürür.

## <a name="op_arrow"></a>move_iterator:: operator-&gt;

Normal bir `RandomIterator` `operator->` gibi, geçerli öğeye ait alanlara erişim sağlar.

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci `&**this` döndürür.

## <a name="pointer"></a>move_iterator::p oınter

Tür `pointer`, `move_iterator` için rastgele Yineleyici `RandomIterator` temel alan bir **typedef** 'dir ve birbirlerinin yerine kullanılabilir.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür `RandomIterator` için bir eş anlamlı.

## <a name="reference"></a>move_iterator:: Reference

@No__t_0 türü, `move_iterator` için `value_type&&` temel alan bir **typedef** 'dir ve `value_type&&` birbirinin yerine kullanılabilir.

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir rvalue başvurusu olan `value_type&&` için bir eş anladır.

## <a name="value_type"></a>move_iterator::value_type

Tür `value_type`, yineleyici nitelik `value_type` temel alınarak bir `move_iterator` `typedef` ve bunun yerine onunla birlikte kullanılabilir.

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik `typename iterator_traits<RandomIterator>::value_type` için bir eş anlamlı.

## <a name="see-also"></a>Ayrıca bkz.

[\<iterator >](../standard-library/iterator.md) \
[Lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) \
[Taşıma Oluşturucuları ve taşıma atama işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md) \
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
