---
title: directory_entry Sınıfı
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::experimental::filesystem::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- filesystem/std::experimental::filesystem::directory_entry::directory_entry
- filesystem/std::experimental::filesystem::directory_entry::operator=
- filesystem/std::experimental::filesystem::directory_entry::assign
- filesystem/std::experimental::filesystem::directory_entry::replace_filename
- filesystem/std::experimental::filesystem::directory_entry::path
- filesystem/std::experimental::filesystem::directory_entry::status
- filesystem/std::experimental::filesystem::directory_entry::symlink_status
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;
- filesystem/std::experimental::filesystem::directory_entry::operator==
- filesystem/std::experimental::filesystem::directory_entry::operator!=
- filesystem/std::experimental::filesystem::directory_entry::operator&lt;=
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;
- filesystem/std::experimental::filesystem::directory_entry::operator&gt;=
ms.assetid: 1827c67b-4137-4548-adb0-f955f7acaf08
helpviewer_keywords:
- std::experimental::filesystem::directory_entry
- std::experimental::filesystem::directory_entry::operator const std::experimental::filesystem::path &
- std::experimental::filesystem::directory_entry::directory_entry
- std::experimental::filesystem::directory_entry::operator=
- std::experimental::filesystem::directory_entry::assign
- std::experimental::filesystem::directory_entry::replace_filename
- std::experimental::filesystem::directory_entry::path
- std::experimental::filesystem::directory_entry::status
- std::experimental::filesystem::directory_entry::symlink_status
- std::experimental::filesystem::directory_entry::operator&lt;
- std::experimental::filesystem::directory_entry::operator==
- std::experimental::filesystem::directory_entry::operator!=
- std::experimental::filesystem::directory_entry::operator&lt;=
- std::experimental::filesystem::directory_entry::operator&gt;
- std::experimental::filesystem::directory_entry::operator&gt;=
ms.openlocfilehash: 35b0dc55bf5db2f799d9ade28cd5968ceab3332b
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458955"
---
# <a name="directoryentry-class"></a>directory_entry Sınıfı

Tarafından `*X`döndürülen bir nesneyi açıklar; burada *X* , bir [Directory_iterator](../standard-library/directory-iterator-class.md) veya [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class directory_entry;
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, [Path](../standard-library/path-class.md)türünde bir nesne depolar. Depolanan `path` , [yol sınıfının](../standard-library/path-class.md) bir örneği veya öğesinden `path`türetilmiş bir tür olabilir. Ayrıca iki [file_type](../standard-library/filesystem-enumerations.md#file_type) değeri de depolar; Bunlardan biri, depolanan dosya adının durumu hakkında ne olduğunu ve dosya adının sembolik bağlantı durumu hakkında bilindiklerinizi temsil eden başka bir şeydir.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[directory_entry](#directory_entry)|Varsayılan olarak belirlenen oluşturucular beklendiği gibi davranır. `mypath` Dördüncü Oluşturucu *Pval*, `mystat` *stat_arg*ve `mysymstat` *symstat_arg*için başlatılır.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[ata](#assign)|Üye işlevi *Pval* `mypath`'yi, *stat* `mystat`ve *symstat* `mysymstat`'yı atar.|
|[Yolu](#path)|Üye işlevi döndürür `mypath`.|
|[replace_filename](#replace_filename)|Üye işlevi `mypath` , *stat_arg*ve `mypath.parent_path()` `mystat`  /    symstat_arg ile birlikte Pval iledeğiştirilir`mysymstat`|
|[status](#status)|Her iki üye işlevi `mystat` de önce değiştirilmiş olabilir.|
|[symlink_status](#symlink_status)|Her iki üye işlevi `mysymstat` de önce değiştirilmiş olabilir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Liste öğelerini başka bir listenin kopyasıyla değiştirir.|
|[operator=](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|
|[operator==](#op_eq)|Döndürür `mypath == right.mypath`.|
|[işleç <](#op_lt)|Döndürür `mypath < right.mypath`.|
|[işleç < =](#op_lteq)|Döndürür `!(right < *this)`.|
|[işleç >](#op_gt)|Döndürür `right < *this`.|
|[operator>=](#op_gteq)|Döndürür `!(*this < right)`.|
|[işleç const path_type &](#path_type)|Döndürür `mypath`.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<deneysel/dosya sistemi&gt;

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="assign"></a>ata

Üye işlevi *Pval* to `mypath`, *stat_arg* to `mystat`ve *symstat_arg* to 'a `mysymstat`atar.

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametreler

*Pval*\
Depolanan dosya adı yolu.

*stat_arg*\
Depolanan dosya adının durumu.

*symstat_arg*\
Depolanan dosya adının sembolik bağlantı durumu.

## <a name="directory_entry"></a>directory_entry

Varsayılan olarak belirlenen oluşturucular beklendiği gibi davranır. `mypath` Dördüncü Oluşturucu *Pval*, `mystat` *stat_arg*ve `mysymstat` *symstat_arg*için başlatılır.

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametreler

*Pval*\
Depolanan dosya adı yolu.

*stat_arg*\
Depolanan dosya adının durumu.

*symstat_arg*\
Depolanan dosya adının sembolik bağlantı durumu.

## <a name="op_neq"></a>işleç! =

Üye işlevi döndürür `!(*this == right)`.

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`directory_entry.

## <a name="op_as"></a>işleç =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine`directory_entry`Kopyalanmakta olan [directory_entry](../standard-library/directory-entry-class.md) .

## <a name="op_eq"></a>işleç = =

Üye işlevi döndürür `mypath == right.mypath`.

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`directory_entry.

## <a name="op_lt"></a>işlecinde&lt;

Üye işlevi döndürür `mypath < right.mypath`.

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`directory_entry.

## <a name="op_lteq"></a>işlecinde&lt;=

Üye işlevi döndürür `!(right < *this)`.

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`directory_entry.

## <a name="op_gt"></a>işlecinde&gt;

Üye işlevi döndürür `right < *this`.

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`directory_entry.

## <a name="op_gteq"></a>işlecinde&gt;=

Üye işlevi döndürür `!(*this < right)`.

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle [](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`directory_entry.

## <a name="path_type"></a>işleç const path_type &

Üye işleci döndürür `mypath`.

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a>Yolun

Üye işlevi döndürür `mypath`.

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a>replace_filename

Üye işlevi `mypath` , *stat_arg*ve `mypath.parent_path()` `mystat`  /    symstat_arg ile birlikte Pval iledeğiştirilir`mysymstat`

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametreler

*Pval*\
Depolanan dosya adı yolu.

*stat_arg*\
Depolanan dosya adının durumu.

*symstat_arg*\
Depolanan dosya adının sembolik bağlantı durumu.

## <a name="status"></a>durumlarına

Her iki üye işlevi `mystat` de önce aşağıdaki gibi değiştirilmiştir:

1. `status_known(mystat)` Ardından hiçbir şey yapmaz.

1. Aksi takdirde, `!status_known(mysymstat) && !is_symlink(mysymstat)`. `mystat = mysymstat`

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*\
Durum hata kodu.

## <a name="symlink_status"></a>symlink_status

Her iki üye işlevi `mysymstat` de önce aşağıdaki gibi değiştirilmiştir: `status_known(mysymstat)` Ardından hiçbir şey yapmaz. Aksi takdirde `mysymstat = symlink_status(mypval)`,.

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*\
Durum hata kodu.

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<Biçimlendiri&gt;](../standard-library/filesystem.md)
