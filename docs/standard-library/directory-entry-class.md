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
ms.openlocfilehash: c1b68aefd44d8f0ac60c36307dee93333d801bb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533828"
---
# <a name="directoryentry-class"></a>directory_entry Sınıfı

Tarafından döndürülen bir nesne tanımlayan `*X`burada *X* olduğu bir [directory_iterator](../standard-library/directory-iterator-class.md) veya [recursive_directory_iterator](../standard-library/recursive-directory-iterator-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class directory_entry;
```

## <a name="remarks"></a>Açıklamalar

Sınıf türünden bir nesne depolar [yolu](../standard-library/path-class.md). Depolanan `path` örneği olabilir [path sınıfı](../standard-library/path-class.md) veya türetilmiş bir türde `path`. İkisi de depolar [file_type](../standard-library/filesystem-enumerations.md#file_type) değerleri; depolanan dosya adının durumunu hakkında bilinen temsil eden, diğeri, dosya adı sembolik bağlantı durumunu hakkında bilinen temsil eder.

Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md).

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[directory_entry](#directory_entry)|Varsayılan haline getirilen oluşturucular beklendiği gibi davranır. Dördüncü Oluşturucu başlatır `mypath` için *pval*, `mystat` için *stat_arg*, ve `mysymstat` için *symstat_arg*.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Ata](#assign)|Üye işlevi atar *pval* için `mypath`, *stat* için `mystat`, ve *symstat* için `mysymstat`.|
|[Yolu](#path)|Üye işlevinin döndürdüğü `mypath`.|
|[replace_filename](#replace_filename)|Üye işlevini değiştiren `mypath` ile `mypath.parent_path()`  /  *pval*, `mystat` ile *stat_arg*, ve `mysymstat` ile *symstat_arg*|
|[Durumu](#status)|Her iki üye işlev dönüş `mystat` büyük olasılıkla ilk değiştirilemez.|
|[symlink_status](#symlink_status)|Her iki üye işlev dönüş `mysymstat` büyük olasılıkla ilk değiştirilemez.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|Listenin öğelerini başka bir liste kopyasıyla değiştirir.|
|[operator=](#op_as)|Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.|
|[operator==](#op_eq)|Döndürür `mypath == right.mypath`.|
|[işleç <](#op_lt)|Döndürür `mypath < right.mypath`.|
|[operator < =](#op_lteq)|Döndürür `!(right < *this)`.|
|[operator >](#op_gt)|Döndürür `right < *this`.|
|[operator>=](#op_gteq)|Döndürür `!(*this < right)`.|
|[işleci const path_type &](#path_type)|Döndürür `mypath`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<Deneysel/dosya sistemi&gt;

**Namespace:** std::experimental::filesystem

## <a name="assign"></a> Ata

Üye işlevi atar *pval* için `mypath`, *stat_arg* için `mystat`, ve *symstat_arg* için `mysymstat`.

```cpp
void assign(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametreler

*pval*<br/>
Depolanan dosya adı yolu.

*stat_arg*<br/>
Depolanan dosya adındaki durumu.

*symstat_arg*<br/>
Depolanan dosya adındaki sembolik bağlantı durumu.

## <a name="directory_entry"></a> directory_entry

Varsayılan haline getirilen oluşturucular beklendiği gibi davranır. Dördüncü Oluşturucu başlatır `mypath` için *pval*, `mystat` için *stat_arg*, ve `mysymstat` için *symstat_arg*.

```cpp
directory_entry() = default;
directory_entry(const directory_entry&) = default;
directory_entry(directory_entry&&) noexcept = default;
explicit directory_entry(const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametreler

*pval*<br/>
Depolanan dosya adı yolu.

*stat_arg*<br/>
Depolanan dosya adındaki durumu.

*symstat_arg*<br/>
Depolanan dosya adındaki sembolik bağlantı durumu.

## <a name="op_neq"></a> işleç! =

Üye işlevinin döndürdüğü `!(*this == right)`.

```cpp
bool operator!=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`.

## <a name="op_as"></a> işleç =

Varsayılan haline getirilen üye atama işleçleri, beklendiği gibi davranır.

```cpp
directory_entry& operator=(const directory_entry&) = default;
directory_entry& operator=(directory_entry&&) noexcept = default;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) içine kopyalanan `directory_entry`.

## <a name="op_eq"></a> işleç ==

Üye işlevinin döndürdüğü `mypath == right.mypath`.

```cpp
bool operator==(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`.

## <a name="op_lt"></a> İşleci&lt;

Üye işlevinin döndürdüğü `mypath < right.mypath`.

```cpp
bool operator<(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`.

## <a name="op_lteq"></a> İşleci&lt;=

Üye işlevinin döndürdüğü `!(right < *this)`.

```cpp
bool operator&lt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`.

## <a name="op_gt"></a> İşleci&gt;

Üye işlevinin döndürdüğü `right < *this`.

```cpp
bool operator&gt;(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`.

## <a name="op_gteq"></a> İşleci&gt;=

Üye işlevinin döndürdüğü `!(*this < right)`.

```cpp
bool operator&gt;=(const directory_entry& right) const noexcept;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
[Directory_entry](../standard-library/directory-entry-class.md) karşılaştırılan `directory_entry`.

## <a name="path_type"></a> işleci const path_type &

Üye işleci döndürür `mypath`.

```cpp
operator const std::experimental::filesystem::path&() const;
```

## <a name="path"></a> Yolu

Üye işlevinin döndürdüğü `mypath`.

```cpp
const std::experimental::filesystem::path& path() const noexcept;
```

## <a name="replace_filename"></a> replace_filename

Üye işlevini değiştiren `mypath` ile `mypath.parent_path()`  /  *pval*, `mystat` ile *stat_arg*, ve `mysymstat` ile *symstat_arg*

```cpp
void replace_filename(
    const std::experimental::filesystem::path& pval,
    file_status stat_arg = file_status(),
    file_status symstat_arg = file_status());
```

### <a name="parameters"></a>Parametreler

*pval*<br/>
Depolanan dosya adı yolu.

*stat_arg*<br/>
Depolanan dosya adındaki durumu.

*symstat_arg*<br/>
Depolanan dosya adındaki sembolik bağlantı durumu.

## <a name="status"></a> Durumu

Her iki üye işlev dönüş `mystat` büyük olasılıkla ilk gibi değiştirilemez:

1. Varsa `status_known(mystat)` hiçbir şey yapma.

1. Aksi takdirde `!status_known(mysymstat) && !is_symlink(mysymstat)` ardından `mystat = mysymstat`.

```cpp
file_status status() const;
file_status status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*<br/>
Durum hata kodu.

## <a name="symlink_status"></a> symlink_status

Her iki üye işlev dönüş `mysymstat` büyük olasılıkla ilk şu şekilde değiştirilmiş: varsa `status_known(mysymstat)` hiçbir şey yapma. Aksi takdirde, `mysymstat = symlink_status(mypval)`.

```cpp
file_status symlink_status() const;
file_status symlink_status(error_code& ec) const noexcept;
```

### <a name="parameters"></a>Parametreler

*EC*<br/>
Durum hata kodu.

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<dosya sistemi&gt;](../standard-library/filesystem.md)<br/>
