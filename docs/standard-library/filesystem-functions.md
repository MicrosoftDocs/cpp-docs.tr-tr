---
title: '&lt;dosya sistemi&gt; işlevleri'
ms.date: 03/27/2019
f1_keywords:
- FILESYSTEM/std::experimental::filesystem::absolute
- FILESYSTEM/std::experimental::filesystem::canonical
- FILESYSTEM/std::experimental::filesystem::copy
- FILESYSTEM/std::experimental::filesystem::copy_file
- FILESYSTEM/std::experimental::filesystem::copy_symlink
- FILESYSTEM/std::experimental::filesystem::create_directories
- FILESYSTEM/std::experimental::filesystem::create_directory
- FILESYSTEM/std::experimental::filesystem::create_directory_symlink
- FILESYSTEM/std::experimental::filesystem::create_hard_link
- FILESYSTEM/std::experimental::filesystem::create_symlink
- FILESYSTEM/std::experimental::filesystem::current_path
- FILESYSTEM/std::experimental::filesystem::equivalent
- FILESYSTEM/std::experimental::filesystem::exists
- FILESYSTEM/std::experimental::filesystem::file_size
- FILESYSTEM/std::experimental::filesystem::hard_link_count
- FILESYSTEM/std::experimental::filesystem::hash_value
- FILESYSTEM/std::experimental::filesystem::is_block_file
- FILESYSTEM/std::experimental::filesystem::is_character_file
- FILESYSTEM/std::experimental::filesystem::is_directory
- FILESYSTEM/std::experimental::filesystem::is_empty
- FILESYSTEM/std::experimental::filesystem::is_fifo
- FILESYSTEM/std::experimental::filesystem::is_other
- FILESYSTEM/std::experimental::filesystem::is_regular_file
- FILESYSTEM/std::experimental::filesystem::is_socket
- FILESYSTEM/std::experimental::filesystem::is_symlink
- FILESYSTEM/std::experimental::filesystem::last_write_time
- FILESYSTEM/std::experimental::filesystem::permissions
- FILESYSTEM/std::experimental::filesystem::read_symlink
- FILESYSTEM/std::experimental::filesystem::remove
- FILESYSTEM/std::experimental::filesystem::remove_all
- FILESYSTEM/std::experimental::filesystem::rename
- FILESYSTEM/std::experimental::filesystem::resize_file
- FILESYSTEM/std::experimental::filesystem::space
- FILESYSTEM/std::experimental::filesystem::status
- FILESYSTEM/std::experimental::filesystem::status_known
- FILESYSTEM/std::experimental::filesystem::swap
- FILESYSTEM/std::experimental::filesystem::symlink_status
- FILESYSTEM/std::experimental::filesystem::system_complete
- FILESYSTEM/std::experimental::filesystem::temp_directory_path
- FILESYSTEM/std::experimental::filesystem::u8path
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
helpviewer_keywords:
- std::experimental::filesystem::absolute
- std::experimental::filesystem::canonical
- std::experimental::filesystem::copy
- std::experimental::filesystem::copy_file
- std::experimental::filesystem::copy_symlink
- std::experimental::filesystem::create_directories
- std::experimental::filesystem::create_directory
- std::experimental::filesystem::create_directory_symlink
- std::experimental::filesystem::create_hard_link
- std::experimental::filesystem::create_symlink
- std::experimental::filesystem::current_path
- std::experimental::filesystem::equivalent
- std::experimental::filesystem::exists
- std::experimental::filesystem::file_size
- std::experimental::filesystem::hard_link_count
- std::experimental::filesystem::hash_value
- std::experimental::filesystem::is_block_file
- std::experimental::filesystem::is_character_file
- std::experimental::filesystem::is_directory
- std::experimental::filesystem::is_empty
- std::experimental::filesystem::is_fifo
- std::experimental::filesystem::is_other
- std::experimental::filesystem::is_regular_file
- std::experimental::filesystem::is_socket
- std::experimental::filesystem::is_symlink
- std::experimental::filesystem::last_write_time
- std::experimental::filesystem::permissions
- std::experimental::filesystem::read_symlink
- std::experimental::filesystem::remove
- std::experimental::filesystem::remove_all
- std::experimental::filesystem::rename
- std::experimental::filesystem::resize_file
- std::experimental::filesystem::space
- std::experimental::filesystem::status
- std::experimental::filesystem::status_known
- std::experimental::filesystem::swap
- std::experimental::filesystem::symlink_status
- std::experimental::filesystem::system_complete
- std::experimental::filesystem::temp_directory_path
- std::experimental::filesystem::u8path
ms.openlocfilehash: 11a1857052dd7c242993e8a19afe26aae3c97c06
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405111"
---
# <a name="ltfilesystemgt-functions"></a>&lt;dosya sistemi&gt; işlevleri

Bu işlevleri ücretsiz [ \<filesystem >](../standard-library/filesystem.md) üstbilgi yolları, dosyaları, çözümlemeyin, dizinleri ve birimleri değiştirme ve sorgu işlemleri gerçekleştirin. Daha fazla bilgi ve kod örnekleri için bkz. [dosya sistemi gezintisi (C++)](../standard-library/file-system-navigation.md).

||||
|-|-|-|
|[Mutlak](#absolute)|[başlayın](#begin)|[Canonical](#canonical)|
|[kopyalama](#copy)|[copy_file](#copy_file)|[copy_symlink](#copy_symlink)|
|[create_directories](#create_directories)|[create_directory](#create_directory)|[create_directory_symlink](#create_directory_symlink)|
|[create_hard_link](#create_hard_link)|[create_symlink](#create_symlink)|[current_path](#current_path)|
|[Son](#end)|[eşdeğeri](#equivalent)|[Var.](#exists)|
|[file_size](#file_size)|[hard_link_count](#hard_link_count)|[hash_value](#hash_value)|
|[is_block_file](#is_block_file)|[is_character_file](#is_character_file)|[is_directory](#is_directory)|
|[is_empty](#is_empty)|[is_fifo](#is_fifo)|[is_other](#is_other)|
|[is_regular_file](#is_regular_file)|[is_socket](#is_socket)|[is_symlink](#is_symlink)|
|[last_write_time](#last_write_time)|[izinleri](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[Yeniden adlandırma](#rename)|
|[resize_file](#resize_file)|[alanı](#space)|[Durumu](#status)|
|[status_known](#status_known)|[değiştirme](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|

## <a name="absolute"></a> Mutlak

```cpp
path absolute(const path& pval, const path& base = current_path());
```

Mutlak yol adına karşılık gelen bir işlevi döndürür *pval* göreli yol adını `base`:

1. Varsa `pval.has_root_name() && pval.has_root_directory()` işlevi döndürür *pval*.

1. Varsa `pval.has_root_name() && !pval.has_root_directory()` işlevi döndürür `pval.root_name()`  /  `absolute(base).root_directory()`  /  `absolute(base).relative_path()`  /  `pval.relative_path()`.

1. Varsa `!pval.has_root_name() && pval.has_root_directory()` işlevi döndürür `absolute(base).root_name()`  /  *pval*.

1. Varsa `!pval.has_root_name() && !pval.has_root_directory()` işlevi döndürür `absolute(base)`  /  *pval*.

## <a name="begin"></a>  başlayın

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Her iki işlev dönüş *iter*.

## <a name="canonical"></a>  Canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Tüm İşlevler mutlak bir yol adı form `pabs = absolute(pval, base)` (veya `pabs = absolute(pval)` temel parametre olmadan aşırı yüklemesi için), ardından adımları aşağıdaki sırayla kurallı bir form azaltın:

1. Her yol bileşenini `X` hangi `is_symlink(X)` olduğu **true** değiştirilir `read_symlink(X)`.

1. Her yol bileşenini `.` (nokta geçerli önceki yol bileşenleri tarafından belirlenen geçerli dizin) kaldırılır.

1. Her yol bileşenleri çiftinin `X` / `..` (nokta nokta geçerli önceki yol bileşenleri tarafından oluşturulan bir üst dizin) kaldırılır.

Ardından işlev döndürür `pabs`.

## <a name="copy"></a>  kopyalama

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

İşlevler büyük olasılıkla tüm kopyalayın veya bir veya daha fazla dosyaları bağlantısını *gelen* için *için* denetiminde *kabul eder*, olarak gerçekleştirilen `copy_options::none` hiçbir ileaşırıyüklemeleriçin*bölgedeyse* parametresi. *bölgedeyse* biri içermesi:

- `skip_existing`, `overwrite_existing`, veya `update_existing`

- `copy_symlinks` veya `skip_symlinks`

- `directories_only`, `create_symlinks`, veya `create_hard_links`

İşlevleri, öncelikle file_status değerlerini belirlemek `f` için *gelen* ve `t` için *için*:

- varsa `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`, çağırarak `symlink_status`

- Aksi takdirde, çağırarak `status`

- Aksi takdirde bir hata rapor.

Varsa `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`, bunlar daha sonra bir hata rapor (ve başka hiçbir şey yapma).

Aksi takdirde `is_symlink(f)` sonra:

- Varsa `options & copy_options::skip_symlinks` hiçbir şey yapma.

- Aksi takdirde `!exists(t)&& options & copy_options::copy_symlinks` ardından `copy_symlink(from, to, opts)`.

- Aksi takdirde bir hata rapor.

Aksi takdirde `is_regular_file(f)` sonra:

- Varsa `opts & copy_options::directories_only` hiçbir şey yapma.

- Aksi takdirde `opts & copy_options::create_symlinks` ardından `create_symlink(to, from)`.

- Aksi takdirde `opts & copy_options::create_hard_links` ardından `create_hard_link(to, from)`.

- Aksi takdirde `is_directory(f)` ardından `copy_file(from, to`  /  `from.filename(), opts)`.

- Aksi takdirde, `copy_file(from, to, opts)`.

Aksi takdirde `is_directory(f) && (opts & copy_options::recursive || !opts)` sonra:

```cpp
if (!exists(t))
{  // copy directory contents recursively
    create_directory(to, from, ec);

    for (directory_iterator next(from), end; ec == error_code() && next != end; ++next)
    {
        copy(next->path(), to / next->path().filename(), opts, ec);
    }
}
```

Aksi takdirde, hiçbir şey yapmayın.

## <a name="copy_file"></a>  copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

İşlevler, tüm büyük olasılıkla dosyayı Kopyala *gelen* için *için* denetiminde *kabul eder*, olarak gerçekleştirilen `copy_options::none` olmadan aşırı yüklemeler için *kabul eder*  parametresi. *bölgedeyse* biri içeriyor `skip_existing`, `overwrite_existing`, veya `update_existing`.

Varsa `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))` sonra rapor dosyası zaten var. bir hata olarak.

Aksi takdirde `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))` dosyanın öznitelikleri ve içeriği kopyalama girişimi *gelen* dosyasına *için*. Kopyalama girişimi başarısız olursa hata olarak bildirin.

İşlevler dönüş **true** kopyalama denenir ve başarılı olur, aksi takdirde **false**.

## <a name="copy_symlink"></a>  copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Varsa `is_directory(from)` işlev çağrıları `create_directory_symlink(from, to)`. Aksi takdirde, çağrı `create_symlink(from, to)`.

## <a name="create_directories"></a>  create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

Gibi bir yol için bir\/b\/c işlevi dizin oluşturur bir ve\/dizini oluşturabilmesi gereken şekilde b bir\/b\/gerektiğinde c. Döndürür **true** yalnızca dizin gerçekten oluşturması halinde *pval*.

## <a name="create_directory"></a>  create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

İşlev dizini *pval* gerektiğinde. Yalnızca gerçekten dizini oluşturur, true döndürür *pval*, bu durumda varolan dosyanın izinlerini kopyalar *attr*, ya da kullanıyorsa `perms::all` olmadan aşırı yüklemeler için *attr*  parametresi.

## <a name="create_directory_symlink"></a>  create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi bağlantı olarak dizine bir sembolik bağlantısını oluşturur. *için*.

## <a name="create_hard_link"></a>  create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi, dizin veya dosya için sabit bir bağlantı olarak bağlantısını oluşturur. *için*.

## <a name="create_symlink"></a>  create_symlink

```cpp
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Bir işlev oluşturur *bağlantı* dosyasına bir sembolik bağlantısını olarak *için*.

## <a name="current_path"></a>  current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Hiçbir parametre işlevleriyle *pval* geçerli dizin için yol adını döndürür. Geçerli dizin kalan işlevleri kümesine *pval*.

## <a name="end"></a>  Son

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

İşlev `directory_iterator()` ve ikinci işlevi döndürür `recursive_directory_iterator()`

## <a name="equivalent"></a>  eşdeğeri

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

İşlevler dönüş **true** yalnızca *sol* ve *doğru* aynı dosya sistemi varlık belirleyin.

## <a name="exists"></a>  Var.

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

İşlev `status_known && stat.type() != file_not_found`. İkinci ve üçüncü oluşturucular dönüş `exists(status(pval))`.

## <a name="file_size"></a>  file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

İşlevler tarafından belirtilen dosyanın bayt cinsinden boyutu döndürür. *pval*, `exists(pval) && is_regular_file(pval)` ve dosya boyutu belirlenebilir. Aksi takdirde bir hata bildirecek ve dönüş `uintmax_t(-1)`.

## <a name="hard_link_count"></a>  hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

İşlev için sabit bağlantılar verir *pval*, veya \-bir hata oluşursa 1.

## <a name="hash_value"></a>  hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

İşlev için bir karma değer döndürür `pval.native()`.

## <a name="is_block_file"></a>  is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::block`. Döndürülecek kalan işlevleri `is_block_file(status(pval))`.

## <a name="is_character_file"></a>  is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::character`. Döndürülecek kalan işlevleri `is_character_file(status(pval))`.

## <a name="is_directory"></a>  is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::directory`. Döndürülecek kalan işlevleri `is_directory_file(status(pval))`.

## <a name="is_empty"></a>  is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Varsa `is_directory(pval)` işlevi döndürür sonra `directory_iterator(pval) == directory_iterator()`; Aksi halde döndürür `file_size(pval) == 0`.

## <a name="is_fifo"></a>  is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::fifo`. Döndürülecek kalan işlevleri `is_fifo(status(pval))`.

## <a name="is_other"></a>  is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::other`. Döndürülecek kalan işlevleri `is_other(status(pval))`.

## <a name="is_regular_file"></a>  is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::regular`. Döndürülecek kalan işlevleri `is_regular_file(status(pval))`.

## <a name="is_socket"></a>  is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::socket`. Döndürülecek kalan işlevleri `is_socket(status(pval))`.

## <a name="is_symlink"></a>  is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

İşlev `stat.type() == file_type::symlink`. Döndürülecek kalan işlevleri `is_symlink(status(pval))`.

## <a name="last_write_time"></a>  last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

İlk iki işlevler için son veri değişikliği zamanı döndürür *pval*, veya `file_time_type(-1)` hata oluşması durumunda. Son iki işlev için son veri değiştirilme saatini ayarlayın *pval* için *new_time*.

## <a name="permissions"></a>  İzinleri

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

İşlevler tarafından belirtilen yol için izinler *pval* için `mask & perms::mask` denetiminde `perms & (perms::add_perms | perms::remove_perms)`. *Maske* biri içeriyor `perms::add_perms` ve `perms::remove_perms`.

Varsa `mask & perms::add_perms` işlevleri izinleri ayarlamak `status(pval).permissions() | mask & perms::mask`. Aksi takdirde `mask & perms::remove_perms` işlevleri izinleri ayarlamak `status(pval).permissions() & ~(mask & perms::mask)`. Aksi takdirde izinler işlevleri kümesine `mask & perms::mask`.

## <a name="read_symlink"></a>  read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

İşlevler bir hata rapor ve dönüş `path()` varsa `!is_symlink(pval)`. Aksi takdirde, İşlevler türünde bir nesne döndürür `path` sembolik bağlantısını içeren.

## <a name="remove"></a>  Kaldır

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

İşlevler dönüş **true** yalnızca `exists(symlink_status(pval))` ve dosyayı başarıyla kaldırıldı. Bir sembolik bağlantısını kendisi kaldırıldıysa, onu atayan dosyası değil değildir.

## <a name="remove_all"></a>  remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

Varsa *pval* bir dizin işlevleri yinelemeli olarak tüm dizin girdisi, ardından giriş kaldırın. Aksi takdirde, arama işlevleri `remove`. Bunlar, başarıyla kaldırılan tüm öğelerin sayısını döndürür.

## <a name="rename"></a>  Yeniden adlandırma

```cpp
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;
```

İşlevleri Yeniden Adlandır *gelen* için *için*. Bir sembolik bağlantısını kendisi yeniden adlandırılmış, atayan dosyası değil değildir.

## <a name="resize_file"></a>  resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

İşlevler bir dosyanın boyutunu değiştirme gibi `file_size(pval) == size`

## <a name="space"></a>  alanı

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

İşlev tarafından belirlenen birim hakkındaki bilgileri döndürür *pval*, bir yapı türü `space_info`. Yapısının `uintmax_t(-1)` için herhangi bir değer belirlenemiyor.

## <a name="status"></a>  Durumu

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

İşlevler pathname durum, dosya türü ve ilişkili izinler döndürür *pval*. Kendi test hedefine sembolik bağlantı olduğu halde bu dosyayı belirtir.

## <a name="status_known"></a>  status_known

```cpp
bool status_known(file_status stat) noexcept;
```

İşlev dönüşleri `stat.type() != file_type::none`

## <a name="swap"></a>  değiştirme

```cpp
void swap(path& left, path& right) noexcept;
```

İşlev içeriğini birbiriyle değiştirir *sol* ve *doğru*.

## <a name="symlink_status"></a>  symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

İşlevler pathname hedefine sembolik bağlantı durumunu, dosya türü ve ilişkili izinler döndürür *pval*. İşlevler, aynı şekilde davranır `status(pval)` dosyası değil, kendi test hedefine sembolik bağlantı olması dışında, belirler.

## <a name="system_complete"></a>  system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

İşlevler, kök adıyla ilişkili geçerli dizini gerekli olarak dikkate alan bir mutlak bir yol adı döndürür. \(İşlevler, POSIX döndürür `absolute(pval)`.\)

## <a name="temp_directory_path"></a>  temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

İşlevler bir yol bir dizin için geçici dosyalar içeren uygun döndürür.

## <a name="u8path"></a>  u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

İlk işlev gibi davranır `path(source)` ve ikinci işlevi gibi davranır `path(first, last)` dışında her durumda belirtilen kaynak dosya bağımsız olarak UTF-8 kodlanmış karakter öğeleri dizisi olarak alınır.
