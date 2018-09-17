---
title: directory_iterator sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/10/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: dca2ecf8-3e69-4644-a83d-705061e10cc8
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: dd5fedb8869533755546089bdee903403f30dcea
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726381"
---
# <a name="directoryiterator-class"></a>directory_iterator Sınıfı

Bir dizin adlarında aracılığıyla dizilerinin bir giriş yineleyici açıklar. Bir yineleyici için `X`, ifade `*X` sınıfın nesne olarak değerlendirilen `directory_entry` dosya adını ve durumunu hakkında bilinen herhangi bir şey sarmalar.

Sınıf türünden bir nesne depolar `path`adlı `mydir` sıralı için dizinin adını temsil eden exposition amaçları ve bir nesne türü için burada `directory_entry` adlı `myentry` burada olan geçerli temsil eder Dizin dizisini de kullanabilirsiniz. Varsayılan oluşturulan nesnenin türü `directory_entry` sahip `mydir` yol dizisi son yineleyiciyi temsil eder.

Örneğin, dizin verilen `abc` girişlerle `def` ve `ghi`, kod:

`for (directory_iterator next(path("abc")), end; next != end; ++next)     visit(next->path());`

' ın arayacağı `visit` bağımsız değişkenleriyle `path("abc/def")` ve `path("abc/ghi")`.

Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class directory_iterator;
```

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[directory_iterator](#directory_iterator)|Bir dizin adlarında aracılığıyla dizilerinin bir giriş yineleyici oluşturur.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Artırma](#increment)|Sonraki dosya dizininde ilerletmek çalışır.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Döndürür `!(*this == right)`.|
|[operator=](#op_as)|Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.|
|[operator==](#op_eq)|Döndürür **true** yalnızca her iki `*this` ve *doğru* dizisi son yineleyiciler veya her ikisi de değil son-ın-dizisi-yineleyiciler şunlardır.|
|[operator *](#op_star)|Döndürür `myentry`.|
|[-> işleci](#op_cast)|Döndürür `&**this`.|
|[operator ++](#op_increment)|Çağrıları `increment()`, ardından döndürür `*this`, veya çağrıları nesnenin bir kopyasını oluşturur `increment()`, daha sonra kopyayı döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<Deneysel/filesystem >

**Namespace:** std::experimental::filesystem

## <a name="directory_iterator"></a> directory_iterator::directory_iterator

İlk Oluşturucu bir dizisi bitiş yineleyici oluşturur. İkinci ve üçüncü oluşturucular deponun *pval* içinde `mydir`, ardından açmak ve okumak deneme `mydir` dizini olarak. Başarılı ilk dosya dizininde depoladıkları varsa `myentry`; Aksi takdirde bunlar dizisi bitiş yineleyici üretmek.

Varsayılan haline getirilen construtors beklendiği gibi davranır.

```cpp
directory_iterator() noexcept;
explicit directory_iterator(const path& pval);

directory_iterator(const path& pval, error_code& ec) noexcept;
directory_iterator(const directory_iterator&) = default;
directory_iterator(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*pval*<br/>
Depolanan dosya adı yolu.

*EC*<br/>
Durum hata kodu.

*directory_iterator*<br/>
Depolanan nesne.

## <a name="increment"></a> directory_iterator::increment

İşlev, sonraki dosya dizininde ilerleyin dener. Başarılı, bu dosya adını depolar, `myentry`; Aksi takdirde bu dizisi bitiş yineleyici üretir.

```cpp
directory_iterator& increment(error_code& ec) noexcept;
```

## <a name="op_neq"></a> directory_iterator::operator! =

Üye işleci döndürür `!(*this == right)`.

```cpp
bool operator!=(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md) karşılaştırılan `directory_iterator`.

## <a name="op_as"></a> directory_iterator::operator =

Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.

```cpp
directory_iterator& operator=(const directory_iterator&) = default;
directory_iterator& operator=(directory_iterator&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md) içine kopyalanan `directory_iterator`.

## <a name="op_eq"></a> directory_iterator::operator ==

Üye işleci döndürür **true** yalnızca her iki `*this` ve *doğru* dizisi son yineleyiciler veya her ikisi de değil son-ın-dizisi-yineleyiciler şunlardır.

```cpp
bool operator==(const directory_iterator& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_iterator](../standard-library/directory-iterator-class.md) karşılaştırılan `directory_iterator`.

## <a name="op_star"></a> directory_iterator::operator *

Üye işleci döndürür `myentry`.

```cpp
const directory_entry& operator*() const;
```

## <a name="op_cast"></a> directory_iterator::operator ->

Üye işlevinin döndürdüğü `&**this`.

```cpp
const directory_entry * operator->() const;
```

## <a name="op_increment"></a> directory_iterator::operator ++

İlk üye işlev çağrıları `increment()`, ardından döndürür `*this`. İkinci üye işlevi çağrıları nesnesinin bir kopyasını getirir `increment()`, daha sonra kopyayı döndürür.

```cpp
directory_iterator& operator++();
directory_iterator& operator++(int);
```

### <a name="parameters"></a>Parametreler

*int*<br/>
Artış sayısını.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
[Dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md)<br/>
