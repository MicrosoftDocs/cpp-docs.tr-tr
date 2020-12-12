---
description: 'Hakkında daha fazla bilgi edinin: directory_entry sınıfı'
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
ms.openlocfilehash: a4a4b69e9f568c19eefae79554838fac5781f3f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324554"
---
# <a name="directory_entry-class"></a>directory_entry Sınıfı

Tarafından döndürülen bir nesneyi açıklar `*X` ; burada *X* bir [Directory_iterator](../standard-library/directory-iterator-class.md) veya [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).

## <a name="syntax"></a>Syntax

```cpp
class directory_entry;
```

## <a name="remarks"></a>Açıklamalar

Sınıfı, [Path](../standard-library/path-class.md)türünde bir nesne depolar. Depolanan, `path` [yol sınıfının](../standard-library/path-class.md) bir örneği veya öğesinden türetilmiş bir tür olabilir `path` . Ayrıca iki [file_type](../standard-library/filesystem-enumerations.md#file_type) değeri de depolar; Bunlardan biri, depolanan dosya adının durumu hakkında ne olduğunu ve dosya adının sembolik bağlantı durumu hakkında bilindiklerinizi temsil eden başka bir şeydir.

Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[directory_entry](#directory_entry)|Varsayılan olarak belirlenen oluşturucular beklendiği gibi davranır. Dördüncü Oluşturucu `mypath` , stat_arg ve symstat_arg olmak üzere *Pval* için başlatılır `mystat`  `mysymstat` . |

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[assign (atamak)](#assign) |Üye işlevi *Pval* 'yi `mypath` , *stat* `mystat` ve *symstat* 'yı atar `mysymstat` .|
|[Yolun](#path)|Üye işlevi döndürür `mypath` .|
|[replace_filename](#replace_filename)|Üye işlevi, `mypath` `mypath.parent_path()`  /   `mystat` *stat_arg* ile ve `mysymstat` *symstat_arg* ile birlikte değiştirilir.|
|[durumlarına](#status)|Her iki üye işlevi de `mystat` önce değiştirilmiş olabilir.|
|[symlink_status](#symlink_status)|Her iki üye işlevi de `mysymstat` önce değiştirilmiş olabilir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç! =](#op_neq)|Liste öğelerini başka bir listenin kopyasıyla değiştirir.|
|[işleç =](#op_as)|Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.|
|[işleç = =](#op_eq)|`mypath == right.mypath` döndürür.|
|[işleç<](#op_lt)|`mypath < right.mypath` döndürür.|
|[işleç<=](#op_lteq)|`!(right < *this)` döndürür.|
|[işleç>](#op_gt)|`right < *this` döndürür.|
|[işleç>=](#op_gteq)|`!(*this < right)` döndürür.|
|[işleç const path_type&](#path_type)|`mypath` döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \< Deneysel/dosya sistemi&gt;

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="assign"></a><a name="assign"></a> ata

Üye işlevi *Pval* 'yi `mypath` , *stat_arg* `mystat` ve *symstat_arg* atar `mysymstat` .

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

## <a name="directory_entry"></a><a name="directory_entry"></a> directory_entry

Varsayılan olarak belirlenen oluşturucular beklendiği gibi davranır. Dördüncü Oluşturucu `mypath` , stat_arg ve symstat_arg olmak üzere *Pval* için başlatılır `mystat`  `mysymstat` . 

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

## <a name="operator"></a><a name="op_neq"></a> işleç! =

Üye işlevi döndürür `!(*this == right)` .

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` .

## <a name="operator"></a><a name="op_as"></a> işleç =

Varsayılan olarak ayarlanmış üye atama işleçleri beklenen şekilde davranır.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*Right*\
İçine kopyalandığı [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` .

## <a name="operator"></a><a name="op_eq"></a> işleç = =

Üye işlevi döndürür `mypath == right.mypath` .

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` .

## <a name="operatorlt"></a><a name="op_lt"></a> işlecinde&lt;

Üye işlevi döndürür `mypath < right.mypath` .

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` .

## <a name="operatorlt"></a><a name="op_lteq"></a> işlecinde&lt;=

Üye işlevi döndürür `!(right < *this)` .

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` .

## <a name="operatorgt"></a><a name="op_gt"></a> işlecinde&gt;

Üye işlevi döndürür `right < *this` .

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` .

## <a name="operatorgt"></a><a name="op_gteq"></a> işlecinde&gt;=

Üye işlevi döndürür `!(*this < right)` .

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*Right*\
İle karşılaştırılan [directory_entry](../standard-library/directory-entry-class.md) `directory_entry` .

## <a name="operator-const-path_type"></a><a name="path_type"></a> işleç const path_type&

Üye işleci döndürür `mypath` .

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a><a name="path"></a> Yolun

Üye işlevi döndürür `mypath` .

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a><a name="replace_filename"></a> replace_filename

Üye işlevi, `mypath` `mypath.parent_path()`  /   `mystat` *stat_arg* ile ve `mysymstat` *symstat_arg* ile birlikte değiştirilir.

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

## <a name="status"></a><a name="status"></a> durumlarına

Her iki üye işlevi de `mystat` önce aşağıdaki gibi değiştirilmiştir:

1. `status_known(mystat)`Ardından hiçbir şey yapmaz.

1. Aksi takdirde, `!status_known(mysymstat) && !is_symlink(mysymstat)` `mystat = mysymstat` .

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*\
Durum hata kodu.

## <a name="symlink_status"></a><a name="symlink_status"></a> symlink_status

Her iki üye işlevi de `mysymstat` önce şu şekilde değiştirilmiş olabilir: `status_known(mysymstat)` hiçbir şey yapmaz. Tersi durumda `mysymstat = symlink_status(mypval)`.

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
