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
ms.openlocfilehash: 4a173ea022f21c454d8edd66f94d2d9b14faa4e1
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460218"
---
# <a name="moveiterator-class"></a>move_iterator Sınıfı

Sınıf şablonu `move_iterator` , Yineleyici için bir sarmalayıcıdır. Move_iterator yineleyicinin onu sarmaladığıyla (depoladığı) aynı davranışı sağlar, yalnız bu öğe bir kopyayı taşıma durumuna çevirerek depolanan yineleyicinin başvuru kaldırma işlecini bir rvalue başvurusuna çevirir. Rvalues hakkında daha fazla bilgi için bkz. [rvalue başvuru bildirimci: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class move_iterator;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, başvuru kaldırılması dışında bir yineleyici gibi davranan bir nesneyi tanımlar. Üye işlevi `Iterator` `base()`yoluyla erişilen türünde, Rastgele erişimli bir yineleyici depolar. İçindeki tüm işlemler doğrudan `move_iterator` depolanan yineleyiciden gerçekleştirilir, ancak `operator*` sonucu bir rvalue başvurusu yapmak `value_type&&` için örtük olarak ' a dönüştürülür.

Bir `move_iterator` bir, Sarmalanan Yineleyici tarafından tanımlanmayan işlemler yeteneğine sahip olabilir. Bu işlemler kullanılmamalıdır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[move_iterator](#move_iterator)|Türündeki `move_iterator`nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iterator_type](#iterator_type)|Şablon parametresi `RandomIterator`için bir eş anlamlı.|
|[iterator_category](#iterator_category)|Aynı adın daha uzun **TypeName** ifadesi için bir eş anlamlı, `iterator_category` yineleyicinin genel yeteneklerini tanımlar.|
|[value_type](#value_type)|Aynı adın daha uzun **TypeName** ifadesi için bir eş anlamlı, `value_type` Yineleyici öğelerinin ne tür olduğunu açıklar.|
|[difference_type](#difference_type)|Aynı adın daha uzun **TypeName** ifadesi için bir eş anlamlı, `difference_type` öğeler arasındaki fark değerlerini ifade etmek için gereken integral türünü açıklar.|
|[çağrısı](#pointer)|Şablon parametresi `RandomIterator`için eş anlamlı.|
|[Başvuru](#reference)|`rvalue` Başvuru`value_type&&`için bir eş anlamlı.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[base](#base)|Üye işlevi, bu `move_iterator`tarafından Sarmalanan saklı yineleyiciyi döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[move_iterator::operator*](#op_star)|Döndürdüğü`(reference)*base().`|
|[move_iterator::operator++](#op_add_add)|Depolanmış yineleyiciyi artırır. Tam davranış artırma öncesi mi artırma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operator--](#operator--)|Depolanan yineleyiciyi azaltır. Tam davranış azaltma öncesi mi azaltma sonrası mı olduğuna bağlıdır.|
|[move_iterator::operator-&gt;](#op_arrow)|Döndürür `&**this`.|
|[move_iterator::operator-](#operator-)|İlk `move_iterator(*this) -=` olarak geçerli konumdan doğru değeri çıkararak döndürür.|
|[move_iterator::operator[]](#op_at)|Döndürür `(reference)*(*this + off)`. Bu konumdaki değeri elde etmek için geçerli temel bir uzaklık belirtmenizi sağlar.|
|[move_iterator::operator+](#op_add)|Değeri `move_iterator(*this) +=` döndürür. Bu konumdaki değeri elde etmek için geçerli temele bir uzaklık eklemenizi sağlar.|
|[move_iterator::operator+=](#op_add_eq)|Depolanan yineleyiciye sağ değeri ekler ve döndürür `*this`.|
|[move_iterator::operator-=](#operator-_eq)|Depolanan yineleyiciden sağ değeri çıkartır ve döndürür `*this`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<Yineleyici >

**Ad alanı:** std

## <a name="base"></a>move_iterator:: Base

Bu `move_iterator`için depolanan yineleyiciyi döndürür.

```cpp
RandomIterator base() const;
```

### <a name="remarks"></a>Açıklamalar

Üye işlevi depolanan yineleyiciyi döndürür.

## <a name="difference_type"></a>  move_iterator::difference_type

Tür `difference_type` ,`move_iterator`Yineleyici nitelik temelalınarakkullanılabilirvebununyerineonunlabirliktekullanılabilir.`difference_type` `typedef`

```cpp
typedef typename iterator_traits<RandomIterator>::difference_type difference_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik `typename iterator_traits<RandomIterator>::pointer`için bir eş anlamlı.

## <a name="iterator_category"></a>move_iterator::iterator_category

Tür `iterator_category` ,`move_iterator`Yineleyici nitelik temelalınarakkullanılabilirvebununyerineonunlabirliktekullanılabilir.`iterator_category` `typedef`

```cpp
typedef typename iterator_traits<RandomIterator>::iterator_category  iterator_category;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik `typename iterator_traits<RandomIterator>::iterator_category`için bir eş anlamlı.

## <a name="iterator_type"></a>move_iterator::iterator_type

Türü `iterator_type` , sınıf `RandomIterator` şablonu`move_iterator`için Şablon parametresine dayalıdır ve yerine birbirinin yerine kullanılabilir.

```cpp
typedef RandomIterator iterator_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi `RandomIterator`için bir eş anlamlı.

## <a name="move_iterator"></a>move_iterator::move_iterator

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

İlk Oluşturucu, saklı yineleyiciyi varsayılan Oluşturucusu ile başlatır. Kalan oluşturucular, depolanan yineleyiciyi ile `base.base()`başlatır.

## <a name="op_add_eq"></a>move_iterator:: operator + =

Depolanan yineleyici için bir konum ekler ve bu sayede saklı Yineleyici yeni geçerli konumdaki öğeyi işaret eder. İşleci ardından yeni geçerli öğeyi taşıtir.

```cpp
move_iterator& operator+=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

*_Kapatma*\
Yeni geçerli konumu belirlemekte geçerli konuma eklenecek bir konum.

### <a name="return-value"></a>Dönüş Değeri

Yeni geçerli öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

İşleci, saklı Yineleyici için *_Kapalı* ekler. Ardından döndürür `*this`.

## <a name="operator-_eq"></a>  move_iterator::operator-=

Belirtilen sayıda önceki öğenin arasında gider. Bu işleç, depolanan yineleyiciden bir sapmayı çıkartır.

```cpp
move_iterator& operator-=(difference_type _Off);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci değerlendirilir `*this += -_Off`. Ardından döndürür `*this`.

## <a name="op_add_add"></a>  move_iterator::operator++

Geçerli öğeye ait `move_iterator.` saklı yineleyiciyi, postıncrement işleci tarafından erişilir. Next öğesine preıncrement işleci tarafından erişilir.

```cpp
move_iterator& operator++();
move_iterator operator++(int);
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

Birincisi (preıncrement) işleci saklı yineleyiciyi arttırır. Ardından döndürür `*this`.

İkinci (postıncrement) işleci bir kopyası `*this`yapar, değerlendirir. `++*this` Sonra kopyayı döndürür.

## <a name="op_add"></a>  move_iterator::operator+

Yineleyici konumunu herhangi bir sayıda öğe tarafından gelişmiş döndürür.

```cpp
move_iterator operator+(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `move_iterator(*this) +=`. `_Off`

## <a name="op_at"></a>move_iterator:: operator []

Dizi dizininin öğe aralığı `move iterator`genelinde öğelere erişimine izin verir.

```cpp
reference operator[](difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `(reference)*(*this + _Off)`.

## <a name="operator--"></a>  move_iterator::operator--

Ön ve geri azaltma üye işleçleri, saklı Yineleyici üzerinde bir azaltma gerçekleştirir.

```cpp
move_iterator& operator--();
move_iterator operator--();
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İlk üye işleci (predecrement) depolanan yineleyiciyi azaltır. Ardından döndürür `*this`.

İkinci (postazaltma) işleci bir kopyası `*this`yapar, değerlendirir. `--*this` Sonra kopyayı döndürür.

## <a name="operator-"></a>move_iterator:: operator-

Depolanan yineleyiciyi azaltır ve belirtilen değeri döndürür.

```cpp
move_iterator operator-(difference_type _Off) const;
```

### <a name="parameters"></a>Parametreler

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `move_iterator(*this) -= _Off`.

## <a name="op_star"></a>  move_iterator::operator*

Saklı yineleyiciden başvurur ve değeri döndürür. Bu, bir `rvalue reference` gibi davranır ve bir taşıma ataması gerçekleştirir. İşleci, geçerli öğeyi temel yineleyiciden aktarır. Aşağıdaki öğesi, yeni geçerli öğe haline gelir.

```cpp
reference operator*() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `(reference)*base()`.

## <a name="op_arrow"></a>move_iterator:: operator-&gt;

`RandomIterator` Normal`operator->`bir şekilde, geçerli öğeye ait alanlara erişim sağlar.

```cpp
pointer operator->() const;
```

### <a name="remarks"></a>Açıklamalar

İşleci döndürülür `&**this`.

## <a name="pointer"></a>move_iterator::p oınter

Türü `pointer` , için `RandomIterator`  rastgeleyineleyicitemelalanbirtypedef'dirvebirbirlerininyerine`move_iterator`kullanılabilir.

```cpp
typedef RandomIterator  pointer;
```

### <a name="remarks"></a>Açıklamalar

Tür için `RandomIterator`bir eş anlamlı.

## <a name="reference"></a>move_iterator:: Reference

`reference` Türü, `value_type&&` için `value_type&&`  temellibirtypedef'dirveilebirbirlerininyerine`move_iterator`kullanılabilir.

```cpp
typedef value_type&& reference;
```

### <a name="remarks"></a>Açıklamalar

Türü, bir rvalue başvurusu olan `value_type&&`için bir eş anladır.

## <a name="value_type"></a>move_iterator::value_type

Tür `value_type` ,`move_iterator`Yineleyici nitelik temelalınarakkullanılabilirvebununyerineonunlabirliktekullanılabilir.`value_type` `typedef`

```cpp
typedef typename iterator_traits<RandomIterator>::value_type   value_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, yineleyici nitelik `typename iterator_traits<RandomIterator>::value_type`için bir eş anlamlı.

## <a name="see-also"></a>Ayrıca bkz.

[\<Yineleyici >](../standard-library/iterator.md)\
[Lvalues ve rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)\
[Taşıma Oluşturucuları ve taşıma atama Işleçleri (C++)](../cpp/move-constructors-and-move-assignment-operators-cpp.md)\
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
