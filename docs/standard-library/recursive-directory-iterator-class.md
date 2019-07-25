---
title: recursive_directory_iterator Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: 98eaf2494a3bc17c0f9d11683fc67fed433ba3a5
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451704"
---
# <a name="recursivedirectoryiterator-class"></a>recursive_directory_iterator Sınıfı

Bir dizindeki dosya adlarıyla sıralı olabilecek, muhtemelen alt dizinlere yinelemeli olarak azalan bir giriş yineleyicisini açıklar. Bir yineleyici `X`için ifade `*X` , dosya adını ve durumu hakkında bilinen her `directory_entry` şeyi sarmalayan bir sınıf nesnesi olarak değerlendirir.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı şunları depolar:

1. Burada `stack<pair<directory_iterator, path>>`, sıralanacak dizinlerin iç içe `mystack` geçme amacını temsil eden Exposition amaçları için aranan bir nesne

1. Burada `directory_entry` çağrılan`myentry` , Dizin dizisindeki geçerli dosya adını temsil eden bir nesne

1. Burada çağrılan `no_push` **bool**türünde bir nesne, alt dizinlere özyinelemeli olarak ne tür bir devre dışı bırakılıp bırakılmadığını kaydeder

1. Burada çağrılan `directory_options` `myoptions` ve oluşturma sırasında belirlenen seçenekleri kaydeden bir nesne.

Türü `recursive_directory_entry` varsayılan olarak oluşturulmuş bir nesne, öğesinde `mystack.top().first` sıra sonu yineleyicisini içerir ve dizi son yineleyiciyi temsil eder. Örneğin, dizinde `def` (bir dizin `abc` ), `def/ghi`ve, ve `jkl`kodu olan dizin verildiğinde:

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

, ve bağımsız değişkenlerle `path("abc/def/ghi")` birlikte ziyareti `path("abc/jkl")`çağırır. Sıralamayı bir dizin alt ağacı aracılığıyla iki şekilde niteleyebilirsiniz:

1. Bir dizin oluşturmaksızın yalnızca `recursive_directory_iterator` değeri `directory_options::follow_directory_symlink`olan bir `directory_options` bağımsız değişkenle birlikte oluşturduysanız taranır.

1. `disable_recursion_pending` Bu durumda, daha sonra bir artış sırasında karşılaşılan bir sonraki dizin, özyinelemeli olarak taranmaz.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Bir `recursive_directory_iterator`oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[derinliğini](#depth)|Değerini `mystack.size() - 1`döndürür, `pval` bu nedenle 0 ' dır.|
|[disable_recursion_pending](#disable_recursion_pending)|İçinde`no_push` **doğru** depolar.|
|[ılamadı](#increment)|Sıradaki dosya adına ilerler.|
|[Seçenekler](#options)|Döndürür `myoptions`.|
|[cağımız](#pop)|Sonraki nesneyi döndürür.|
|[recursion_pending](#recursion_pending)|Döndürür `!no_push`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Döndürür `!(*this == right)`.|
|[operator=](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|
|[operator==](#op_eq)|Yalnızca  `*this` ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse true değerini döndürür.|
|[işlecinde](#op_multiply)|Döndürür `myentry`.|
|[operator->](#op_cast)|Döndürür `&**this`.|
|[işleç + +](#op_increment)|Değerini artırır `recursive_directory_iterator`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<dosya sistemi >

**Ad alanı:** std:: TR2:: sys

## <a name="depth"></a>recursive_directory_iterator::d epth

Değerini `mystack.size() - 1`döndürür, `pval` bu nedenle 0 ' dır.

```cpp
int depth() const;
```

## <a name="disable_recursion_pending"></a>recursive_directory_iterator::d isable_recursion_pending

İçinde`no_push` **doğru** depolar.

```cpp
void disable_recursion_pending();
```

## <a name="increment"></a>recursive_directory_iterator:: Increment

Sıradaki dosya adına ilerler.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*\
Belirtilen hata kodu.

### <a name="remarks"></a>Açıklamalar

İşlev, iç içe dizideki bir sonraki dosya adına ilerle çalışır. Başarılı olursa, bu dosya adını ' de `myentry`depolar; Aksi takdirde, sıra sonu Yineleyici oluşturur.

## <a name="op_neq"></a>recursive_directory_iterator:: operator! =

Döndürür `!(*this == right)`.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırma için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="op_as"></a>recursive_directory_iterator:: operator =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*recursive_directory_iterator*\
İçine`recursive_directory_iterator`Kopyalanmakta olan [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="op_eq"></a>recursive_directory_iterator:: operator = =

Yalnızca  `*this` ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse true değerini döndürür.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırma için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="op_multiply"></a>recursive_directory_iterator:: operator *

Döndürür `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a>recursive_directory_iterator:: operator->

Döndürür `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>recursive_directory_iterator:: operator + +

Değerini artırır `recursive_directory_iterator`.

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parametreler

*'tir*\
Belirtilen artış.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi çağırır `increment()`ve sonra döndürür. `*this` İkinci üye işlevi nesnenin bir kopyasını yapar, çağırır `increment()`ve sonra kopyayı döndürür.

## <a name="options"></a>recursive_directory_iterator:: Options

Döndürür `myoptions`.

```cpp
directory_options options() const;
```

## <a name="pop"></a>recursive_directory_iterator::p op

Sonraki nesneyi döndürür.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

Nesne `depth() == 0` bir sıra sonu yineleyicisi olursa. Aksi takdirde, üye işlevi geçerli (ayrıntılı) dizinin taranmasını sonlandırır ve bir sonraki daha düşük derinlikte devam eder.

## <a name="recursion_pending"></a>recursive_directory_iterator::recursion_pending

Döndürür `!no_push`.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iterator"></a>recursive_directory_iterator::recursive_directory_iterator

Bir `recursive_directory_iterator`oluşturur.

```cpp
recursive_directory_iterator() noexcept;
explicit recursive_directory_iterator(const path& pval);

recursive_directory_iterator(const path& pval,
    error_code& ec) noexcept;
recursive_directory_iterator(const path& pval,
    directory_options opts);

recursive_directory_iterator(const path& pval,
    directory_options opts,
    error_code& ec) noexcept;
recursive_directory_iterator(const recursive_directory_iterator&) = default;
recursive_directory_iterator(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Pval*\
Belirtilen yol.

*error_code*\
Belirtilen hata kodu.

*OptIn*\
Belirtilen dizin seçenekleri.

*recursive_directory_iterator*\
`recursive_directory_iterator` Oluşturulan`recursive_directory_iterator` öğesinin bir kopyalama olduğu yer.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir dizi sonu yineleyiciyi üretir. İkinci ve üçüncü oluşturucular içinde `no_push` ve `directory_options::none` `myoptions`içinde **yanlış** bir şekilde depolar, ardından bir dizin olarak *Pval* 'i açıp okumaya çalışır. Başarılı olursa, iç içe `mystack` geçmiş `myentry` dizideki ilk dizin olmayan dosya adını tasarlarlar ve bunları başlatır, aksi takdirde bir dizi son yineleyiciyi üretir.

Dördüncü ve beşinci oluşturucular, ikinci ve üçüncü  `myoptions`ile aynı şekilde davranır. Varsayılan olarak construtors beklendiği gibi davranır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<dosya sistemi >](../standard-library/filesystem.md)\
[Dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)
