---
description: 'Hakkında daha fazla bilgi edinin: recursive_directory_iterator sınıfı'
title: recursive_directory_iterator Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::recursive_directory_iterator
ms.assetid: 79a061bd-5b64-404c-97e8-749c888c2ced
ms.openlocfilehash: b9b5909c62a745233362eeac1adb879c1585098c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337903"
---
# <a name="recursive_directory_iterator-class"></a>recursive_directory_iterator Sınıfı

Bir dizindeki dosya adlarıyla sıralı olabilecek, muhtemelen alt dizinlere yinelemeli olarak azalan bir giriş yineleyicisini açıklar. Bir yineleyici için `X` ifade, `*X` `directory_entry` dosya adını ve durumu hakkında bilinen her şeyi sarmalayan bir sınıf nesnesi olarak değerlendirir.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Syntax

```cpp
class recursive_directory_iterator;
```

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu şunları depolar:

1. `stack<pair<directory_iterator, path>>` `mystack` burada, sıralanacak dizinlerin iç içe geçme amacını temsil eden Exposition amaçları için aranan bir nesne

1. `directory_entry` `myentry` burada çağrılan, Dizin dizisindeki geçerli dosya adını temsil eden bir nesne

1. **`bool`** burada çağrılan, burada çağrılan ve `no_push` özyinelemeli olarak alt dizinlere ayrılan bir nesne devre dışı olup olmadığını kaydeden bir nesne

1. `directory_options`burada çağrılan ve `myoptions` oluşturma sırasında belirlenen seçenekleri kaydeden bir nesne.

Türü varsayılan olarak oluşturulmuş bir nesne `recursive_directory_entry` , öğesinde sıra sonu yineleyicisini içerir `mystack.top().first` ve dizi son yineleyiciyi temsil eder. Örneğin, dizinde `abc` `def` (bir dizin), `def/ghi` ve, ve kodu olan dizin verildiğinde `jkl` :

```cpp
for (recursive_directory_iterator next(path("abc")), end; next != end; ++next)
    visit(next->path());
```

, ve bağımsız değişkenlerle birlikte `path("abc/def/ghi")` ziyareti çağırır `path("abc/jkl")` . Sıralamayı bir dizin alt ağacı aracılığıyla iki şekilde niteleyebilirsiniz:

1. Bir dizin oluşturmaksızın yalnızca değeri olan bir `recursive_directory_iterator` bağımsız değişkenle birlikte oluşturduysanız taranır `directory_options` `directory_options::follow_directory_symlink` .

1. Bu durumda, `disable_recursion_pending` daha sonra bir artış sırasında karşılaşılan bir sonraki dizin, özyinelemeli olarak taranmaz.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[recursive_directory_iterator](#recursive_directory_iterator)|Bir oluşturur `recursive_directory_iterator` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[derinliğini](#depth)|Değerini döndürür `mystack.size() - 1` , bu nedenle `pval` 0 ' dır.|
|[disable_recursion_pending](#disable_recursion_pending)|**`true`** İçinde depolar `no_push` .|
|[ılamadı](#increment)|Sıradaki dosya adına ilerler.|
|[Seçenekler](#options)|`myoptions` döndürür.|
|[cağımız](#pop)|Sonraki nesneyi döndürür.|
|[recursion_pending](#recursion_pending)|`!no_push` döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! =](#op_neq)|`!(*this == right)` döndürür.|
|[işleç =](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|
|[işleç = =](#op_eq)|**`true`** Yalnızca **`*this`** ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse döndürür.|
|[işlecinde](#op_multiply)|`myentry` döndürür.|
|[operator->](#op_cast)|`&**this` döndürür.|
|[işleç + +](#op_increment)|Değerini artırır `recursive_directory_iterator` .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<filesystem>

**Ad alanı:** std:: TR2:: sys

## <a name="recursive_directory_iteratordepth"></a><a name="depth"></a> recursive_directory_iterator::d epth

Değerini döndürür `mystack.size() - 1` , bu nedenle `pval` 0 ' dır.

```cpp
int depth() const;
```

## <a name="recursive_directory_iteratordisable_recursion_pending"></a><a name="disable_recursion_pending"></a> recursive_directory_iterator::d isable_recursion_pending

**`true`** İçinde depolar `no_push` .

```cpp
void disable_recursion_pending();
```

## <a name="recursive_directory_iteratorincrement"></a><a name="increment"></a> recursive_directory_iterator:: Increment

Sıradaki dosya adına ilerler.

```cpp
recursive_directory_iterator& increment(error_code& ec) noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*\
Belirtilen hata kodu.

### <a name="remarks"></a>Açıklamalar

İşlev, iç içe dizideki bir sonraki dosya adına ilerle çalışır. Başarılı olursa, bu dosya adını ' de depolar `myentry` ; Aksi takdirde, sıra sonu Yineleyici oluşturur.

## <a name="recursive_directory_iteratoroperator"></a><a name="op_neq"></a> recursive_directory_iterator:: operator! =

`!(*this == right)` döndürür.

```cpp
bool operator!=(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırma için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="recursive_directory_iteratoroperator"></a><a name="op_as"></a> recursive_directory_iterator:: operator =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
recursive_directory_iterator& operator=(const recursive_directory_iterator&) = default;
recursive_directory_iterator& operator=(recursive_directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*recursive_directory_iterator*\
İçine kopyalandığı [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) `recursive_directory_iterator` .

## <a name="recursive_directory_iteratoroperator"></a><a name="op_eq"></a> recursive_directory_iterator:: operator = =

**`true`** Yalnızca **`*this`** ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse döndürür.

```cpp
bool operator==(const recursive_directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Karşılaştırma için [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md) .

## <a name="recursive_directory_iteratoroperator"></a><a name="op_multiply"></a> recursive_directory_iterator:: operator *

`myentry` döndürür.

```cpp
const directory_entry& operator*() const;
```

## <a name="recursive_directory_iteratoroperator-"></a><a name="op_cast"></a> recursive_directory_iterator:: operator->

`&**this` döndürür.

```cpp
const directory_entry * operator->() const;
```

## <a name="recursive_directory_iteratoroperator"></a><a name="op_increment"></a> recursive_directory_iterator:: operator + +

Değerini artırır `recursive_directory_iterator` .

```cpp
recursive_directory_iterator& operator++();

recursive_directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parametreler

*'tir*\
Belirtilen artış.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi çağırır `increment()` ve sonra döndürür **`*this`** . İkinci üye işlevi nesnenin bir kopyasını yapar, çağırır ve `increment()` sonra kopyayı döndürür.

## <a name="recursive_directory_iteratoroptions"></a><a name="options"></a> recursive_directory_iterator:: seçenekler

`myoptions` döndürür.

```cpp
directory_options options() const;
```

## <a name="recursive_directory_iteratorpop"></a><a name="pop"></a> recursive_directory_iterator::p op

Sonraki nesneyi döndürür.

```cpp
void pop();
```

### <a name="remarks"></a>Açıklamalar

`depth() == 0`Nesne bir sıra sonu yineleyicisi olursa. Aksi takdirde, üye işlevi geçerli (ayrıntılı) dizinin taranmasını sonlandırır ve bir sonraki daha düşük derinlikte devam eder.

## <a name="recursive_directory_iteratorrecursion_pending"></a><a name="recursion_pending"></a> recursive_directory_iterator:: recursion_pending

`!no_push` döndürür.

```cpp
bool recursion_pending() const;
```

## <a name="recursive_directory_iteratorrecursive_directory_iterator"></a><a name="recursive_directory_iterator"></a> recursive_directory_iterator:: recursive_directory_iterator

Bir oluşturur `recursive_directory_iterator` .

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
`recursive_directory_iterator`Oluşturulan öğesinin `recursive_directory_iterator` bir kopyalama olduğu yer.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu bir dizi sonu yineleyiciyi üretir. İkinci ve üçüncü oluşturucular içinde ve ' de depolar **`false`** `no_push` `directory_options::none` `myoptions` , ardından bir dizin olarak *Pval* 'yi açmayı ve okumayı dener. Başarılı olursa, `mystack` `myentry` iç içe geçmiş dizideki ilk dizin olmayan dosya adını tasarlarlar ve bunları başlatır, aksi takdirde bir dizi son yineleyiciyi üretir.

Dördüncü ve beşinci oluşturucular, ikinci ve üçüncü ile *aynı şekilde davranır* `myoptions` . Varsayılan olarak construtors beklendiği gibi davranır.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)
