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
ms.openlocfilehash: 8c6dcce3de32c7e25d2489cb508454dff500a1a6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454420"
---
# <a name="directoryiterator-class"></a>directory_iterator Sınıfı

Dizindeki dosya adlarıyla sıraleyen bir giriş yineleyicisini açıklar. Bir yineleyici `X`için ifade `*X` , dosya adını ve durumu hakkında bilinen her `directory_entry` şeyi sarmalayan bir sınıf nesnesi olarak değerlendirir.

`path`Sınıfı, burada adlı `mydir` bir nesne depolar, bu, sıralanacak dizinin adını temsil eder `directory_entry` ve burada çağrılan `myentry` bir nesne, geçerli Dizin dizisinde dosya adı. Türü `directory_entry` varsayılan olarak oluşturulmuş bir nesne, boş `mydir` bir yol adına sahiptir ve dizi son yineleyiciyi temsil eder.

Örneğin, bir dizin `abc` ve girişleri `def` ve `ghi`kodu:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

, bağımsız `visit` değişkenlerle `path("abc/def")` ve`path("abc/ghi")`ile çağracaktır.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

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
|[operator!=](#op_neq)|Döndürür `!(*this == right)`.|
|[operator=](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|
|[operator==](#op_eq)|Yalnızca  `*this` ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse true değerini döndürür.|
|[işlecinde](#op_star)|Döndürür `myentry`.|
|[operator->](#op_cast)|Döndürür `&**this`.|
|[işleç + +](#op_increment)|Çağırır `increment()`, sonra döndürür `*this`veya nesnenin bir kopyasını, çağırır `increment()`ve sonra kopyayı döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<deneysel/FileSystem >

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="directory_iterator"></a>Directory_iterator::d irectory_iterator

İlk Oluşturucu bir dizi sonu yineleyiciyi üretir. İkinci ve üçüncü oluşturucular içindeki `mydir` *Pval* 'yi depolar, ardından dizin olarak açmayı ve okumayı `mydir` dener. Başarılı olursa, ilk dosya adını içindeki `myentry`dizininde depolar; Aksi takdirde, bir dizi son yineleyicisi oluşturur.

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

## <a name="increment"></a>Directory_iterator:: Increment

İşlev, dizindeki bir sonraki dosya adına ilerle çalışır. Başarılı olursa, bu dosya adını ' de `myentry`depolar; Aksi takdirde, sıra sonu Yineleyici oluşturur.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a>Directory_iterator:: operator! =

Üye işleci döndürür `!(*this == right)`.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-iterator-class.md) karşılaştırılan `directory_iterator`Directory_iterator.

## <a name="op_as"></a>Directory_iterator:: operator =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine`directory_iterator`Kopyalanmakta olan [Directory_iterator](../standard-library/directory-iterator-class.md) .

## <a name="op_eq"></a>Directory_iterator:: operator = =

Üye işleci yalnızca `*this` ve *sağ* sıralı yineleyiciler ise veya her ikisi de dizi sırası yineleyiciler değilse **true** değerini döndürür.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-iterator-class.md) karşılaştırılan `directory_iterator`Directory_iterator.

## <a name="op_star"></a>Directory_iterator:: operator *

Üye işleci döndürür `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a>Directory_iterator:: operator->

Üye işlevi döndürür `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a>Directory_iterator:: operator + +

İlk üye işlevi çağırır `increment()`ve sonra döndürür. `*this` İkinci üye işlevi nesnenin bir kopyasını yapar, çağırır `increment()`ve sonra kopyayı döndürür.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parametreler

*'tir*\
Artımlar sayısı.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<dosya sistemi >](../standard-library/filesystem.md)\
[Dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)
