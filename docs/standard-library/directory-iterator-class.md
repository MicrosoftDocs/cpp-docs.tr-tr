---
title: directory_iterator Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_iterator
- filesystem/std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::directory_iterator
- filesystem/std::experimental::filesystem::directory_iterator::increment
- filesystem/std::experimental::filesystem::directory_iterator::operator=
- filesystem/std::experimental::filesystem::directory_iterator::operator==
- filesystem/std::experimental::filesystem::directory_iterator::operator!=
- filesystem/std::experimental::filesystem::directory_iterator::operator*
- filesystem/std::experimental::filesystem::directory_iterator::operator-&gt;
- filesystem/std::experimental::filesystem::directory_iterator::operator++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
helpviewer_keywords:
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::_Directory_iterator::_Directory_iterator
- std::experimental::filesystem::directory_iterator
- std::experimental::filesystem::directory_iterator::directory_iterator
- std::experimental::filesystem::directory_iterator::increment
- std::experimental::filesystem::directory_iterator::operator=
- std::experimental::filesystem::directory_iterator::operator==
- std::experimental::filesystem::directory_iterator::operator!=
- std::experimental::filesystem::directory_iterator::operator*
- std::experimental::filesystem::directory_iterator::operator-&gt;
- std::experimental::filesystem::directory_iterator::operator++
ms.openlocfilehash: a7ccc2a941da079e14092af5b81dc537db4a48c0
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215783"
---
# <a name="directory_iterator-class"></a>directory_iterator Sınıfı

Dizindeki dosya adlarıyla sıraleyen bir giriş yineleyicisini açıklar. Bir yineleyici için `X` ifade, `*X` `directory_entry` dosya adını ve durumu hakkında bilinen her şeyi sarmalayan bir sınıf nesnesi olarak değerlendirir.

Sınıfı, burada adlı bir nesne depolar, `path` `mydir` Bu, sıralanacak dizinin adını temsil eder ve burada çağrılan bir nesne, `directory_entry` `myentry` Dizin dizisindeki geçerli dosya adını temsil eder. Türü varsayılan olarak oluşturulmuş bir nesne `directory_entry` , boş bir `mydir` yol adına sahiptir ve dizi son yineleyiciyi temsil eder.

Örneğin, bir dizin `abc` `def` ve girişleri ve `ghi` kodu:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

`visit`, bağımsız değişkenlerle ve ile çağracaktır `path("abc/def")` `path("abc/ghi")` .

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class directory_iterator;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[directory_iterator](#directory_iterator)|Dizindeki dosya adlarıyla dizan bir giriş yineleyicisi oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ılamadı](#increment)|Dizindeki bir sonraki dosya adına ilerlemesine çalışır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! =](#op_neq)|`!(*this == right)` döndürür.|
|[işleç =](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|
|[işleç = =](#op_eq)|**`true`** Yalnızca **`*this`** ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse döndürür.|
|[işlecinde](#op_star)|`myentry` döndürür.|
|[operator->](#op_cast)|`&**this` döndürür.|
|[işleç + +](#op_increment)|Çağırır, `increment()` sonra döndürür **`*this`** veya nesnenin bir kopyasını, çağırır ve `increment()` sonra kopyayı döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<experimental/filesystem>

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="directory_iteratordirectory_iterator"></a><a name="directory_iterator"></a>directory_iterator::d irectory_iterator

İlk Oluşturucu bir dizi sonu yineleyiciyi üretir. İkinci ve üçüncü oluşturucular içindeki *Pval* 'yi depolar `mydir` , ardından dizin olarak açmayı ve okumayı dener `mydir` . Başarılı olursa, ilk dosya adını içindeki dizininde depolar `myentry` ; Aksi takdirde, bir dizi son yineleyicisi oluşturur.

Varsayılan olarak construtors beklendiği gibi davranır.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Pval*\
Depolanan dosya adı yolu.

*EC*\
Durum hata kodu.

*directory_iterator*\
Saklı nesne.

## <a name="directory_iteratorincrement"></a><a name="increment"></a>directory_iterator:: Increment

İşlev, dizindeki bir sonraki dosya adına ilerle çalışır. Başarılı olursa, bu dosya adını ' de depolar `myentry` ; Aksi takdirde, sıra sonu Yineleyici oluşturur.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="directory_iteratoroperator"></a><a name="op_neq"></a>directory_iterator:: operator! =

Üye işleci döndürür `!(*this == right)` .

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [Directory_iterator](../standard-library/directory-iterator-class.md) `directory_iterator` .

## <a name="directory_iteratoroperator"></a><a name="op_as"></a>directory_iterator:: operator =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine kopyalandığı [Directory_iterator](../standard-library/directory-iterator-class.md) `directory_iterator` .

## <a name="directory_iteratoroperator"></a><a name="op_eq"></a>directory_iterator:: operator = =

Üye işleci **`true`** yalnızca **`*this`** ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse döndürür.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [Directory_iterator](../standard-library/directory-iterator-class.md) `directory_iterator` .

## <a name="directory_iteratoroperator"></a><a name="op_star"></a>directory_iterator:: operator *

Üye işleci döndürür `myentry` .

```cpp
const directory_entry& operator*() const;
```

## <a name="directory_iteratoroperator-"></a><a name="op_cast"></a>directory_iterator:: operator->

Üye işlevi döndürür `&**this` .

```cpp
const directory_entry * operator->() const;
```

## <a name="directory_iteratoroperator"></a><a name="op_increment"></a>directory_iterator:: operator + +

İlk üye işlevi çağırır `increment()` ve sonra döndürür **`*this`** . İkinci üye işlevi nesnenin bir kopyasını yapar, çağırır ve `increment()` sonra kopyayı döndürür.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parametreler

*'tir*\
Artımlar sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[Dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)
