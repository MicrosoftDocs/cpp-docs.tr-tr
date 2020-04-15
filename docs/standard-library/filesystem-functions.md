---
title: '&lt;dosya&gt; sistemi fonksiyonları'
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
ms.openlocfilehash: f1b48ed6f533d4ccb5f9ef5e6dbcbd6e5cc4f7a1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332043"
---
# <a name="ltfilesystemgt-functions"></a>&lt;dosya&gt; sistemi fonksiyonları

[ \<Dosya sistemindeki](../standard-library/filesystem.md) bu boş işlevler>üstbilgi, yollar, dosyalar, sempozyumlar, dizinler ve birimler üzerinde değiştirme ve sorgu işlemleri yapar. Daha fazla bilgi ve kod örnekleri için [Dosya Sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md)bakın.

## <a name="absolute"></a><a name="absolute"></a>Mutlak

```cpp
path absolute(const path& pval, const path& base = current_path());
```

İşlev, yol adına `base`göre *pval'a* karşılık gelen mutlak yol adını döndürür:

1. Fonksiyon `pval.has_root_name() && pval.has_root_directory()` *pval*döndürür.

1. Fonksiyon `pval.has_root_name() && !pval.has_root_directory()` `pval.root_name()`  /  `absolute(base).root_directory()`  / dönerse. `absolute(base).relative_path()`  /  `pval.relative_path()`

1. Fonksiyon `!pval.has_root_name() && pval.has_root_directory()` `absolute(base).root_name()`  /  *pval*döndürür.

1. Fonksiyon `!pval.has_root_name() && !pval.has_root_directory()` `absolute(base)`  /  *pval*döndürür.

## <a name="begin"></a><a name="begin"></a>Başlamak

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Her iki işlev de *yinelemeyi*döndürer.

## <a name="canonical"></a><a name="canonical"></a>Kurallı

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Tüm işlevler mutlak bir `pabs = absolute(pval, base)` yol `pabs = absolute(pval)` adı oluşturur (veya temel parametresi olmayan aşırı yük için), ardından aşağıdaki adım dizisinde kanonik bir forma indirgeyin:

1. **Doğru** olan `X` `is_symlink(X)` her yol bileşeni nin `read_symlink(X)`yerine .

1. Her yol `.` bileşeni (nokta önceki yol bileşenleri tarafından kurulan geçerli dizin) kaldırılır.

1. Her çift yol `X` / `..` bileşeni (nokta nokta önceki yol bileşenleri tarafından kurulan üst dizini) kaldırılır.

İşlev daha `pabs`sonra döndürür.

## <a name="copy"></a><a name="copy"></a>Kopya

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Fonksiyonların tümü muhtemelen bir veya daha *from* fazla *to* dosyayı *opts*kopyalar veya bağlar, `copy_options::none` bu da tercih *parametresi* olmayan aşırı yükler için alınır. *opts* en fazla birini içerecektir:

- `skip_existing`, `overwrite_existing`veya`update_existing`

- `copy_symlinks` veya `skip_symlinks`

- `directories_only`, `create_symlinks`veya`create_hard_links`

Fonksiyonlar ilk olarak `f` aşağıdakiler `t` *için* file_status değerlerini *belirler:*

- if `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`, arayarak`symlink_status`

- aksi takdirde, arayarak`status`

- Aksi takdirde bir hata bildirin.

Eğer, `!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`daha sonra bir hata rapor (ve başka bir şey).

Aksi takdirde, eğer: `is_symlink(f)`

- Eğer, `options & copy_options::skip_symlinks`o zaman hiçbir şey yapma.

- Aksi takdirde, `!exists(t)&& options & copy_options::copy_symlinks` `copy_symlink(from, to, opts)`eğer , o zaman .

- Aksi takdirde, bir hata bildirin.

Aksi takdirde, eğer `is_regular_file(f)`, sonra:

- Eğer, `opts & copy_options::directories_only`o zaman hiçbir şey yapma.

- Aksi takdirde, `opts & copy_options::create_symlinks` `create_symlink(to, from)`eğer , o zaman .

- Aksi takdirde, `opts & copy_options::create_hard_links` `create_hard_link(to, from)`eğer , o zaman .

- Aksi `is_directory(f)`takdirde, `copy_file(from, to`  /  `from.filename(), opts)`eğer , o zaman .

- Tersi durumda `copy_file(from, to, opts)`.

Aksi takdirde, eğer `is_directory(f) && (opts & copy_options::recursive || !opts)`, sonra:

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

Yoksa hiçbir şey yapma.

## <a name="copy_file"></a><a name="copy_file"></a>copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

İşlevler muhtemelen dosyayı *from* *tercihlerin*denetimi *altında* olduğundan kopyalar, `copy_options::none` bu da *tercih* parametresi olmayan aşırı yükler için alınır. *opts* en fazla birini `skip_existing` `overwrite_existing`içerecektir `update_existing`, veya .

Eğer, `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))`daha sonra dosya zaten var olduğunu bir hata olarak bildirin.

Aksi takdirde, eğer `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))`, daha sonra dosyanın *from* içeriğini ve özniteliklerini *dosyaya*kopyalamaya çalışırsanız. Kopyalama denemesi başarısız olursa hata olarak bildirin.

Kopya denenir ve başarılı olursa, aksi takdirde **yanlış**işlevler **doğru** döndürün.

## <a name="copy_symlink"></a><a name="copy_symlink"></a>copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Eğer `is_directory(from)`, işlev `create_directory_symlink(from, to)`çağırır . Aksi takdirde, `create_symlink(from, to)`çağırır .

## <a name="create_directories"></a><a name="create_directories"></a>create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

\/B\/c gibi bir yol adı için işlev, gerektiğinde\/a ve b dizinleri oluşturur,\/\/böylece gerektiğinde a b c dizini oluşturabilir. Gerçekten dizin *pval*oluşturur sadece **doğru** döndürür.

## <a name="create_directory"></a><a name="create_directory"></a>create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

İşlev gerektiğinde dizin *pval* oluşturur. Yalnızca dizin *pval'ını*oluşturursa doğru döndürür , bu durumda varolan *dosyaattr'dan*izinleri kopyalar veya `perms::all` *attr* parametresi olmayan aşırı yüklemeleri kullanır.

## <a name="create_directory_symlink"></a><a name="create_directory_symlink"></a>create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlev, *dizin*için bir symlink olarak bağlantı oluşturur.

## <a name="create_hard_link"></a><a name="create_hard_link"></a>create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

İşlev, dizin veya *dosyaya*sabit bir bağlantı olarak bağlantı oluşturur.

## <a name="create_symlink"></a><a name="create_symlink"></a>create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlev *dosyaya*bir symlink olarak *bağlantı* oluşturur.

## <a name="current_path"></a><a name="current_path"></a>current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Parametre *pval* olmayan işlevler geçerli dizinin yol adını döndürer. Kalan işlevler geçerli dizini *pval*olarak ayarlar.

## <a name="end"></a><a name="end"></a>Son -unda

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

İlk işlev `directory_iterator()` döndürür ve ikinci işlev döner`recursive_directory_iterator()`

## <a name="equivalent"></a><a name="equivalent"></a>Eşdeğer

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

İşlevler yalnızca *sol* ve *sağ* aynı dosya sistemi varlığını seçerse **doğru** döndürülmez.

## <a name="exists"></a><a name="exists"></a>Var

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

İlk işlev `status_known && stat.type() != file_not_found`döndürür. İkinci ve üçüncü `exists(status(pval))`işlevler döndürülmez.

## <a name="file_size"></a><a name="file_size"></a>file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

Fonksiyonlar *pval*tarafından seçilen dosyanın baytboyutu döndürebilir , eğer `exists(pval) && is_regular_file(pval)` ve dosya boyutu belirlenebilir. Aksi takdirde bir hata `uintmax_t(-1)`rapor ve dönüş .

## <a name="hard_link_count"></a><a name="hard_link_count"></a>hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

*İşlev, pval*için sabit bağlantı \-sayısını veya bir hata oluşursa 1'i döndürür.

## <a name="hash_value"></a><a name="hash_value"></a>hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

İşlev için `pval.native()`karma değer döndürür.

## <a name="is_block_file"></a><a name="is_block_file"></a>is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::block`döndürür. Kalan işlevler `is_block_file(status(pval))`döndürün.

## <a name="is_character_file"></a><a name="is_character_file"></a>is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::character`döndürür. Kalan işlevler `is_character_file(status(pval))`döndürün.

## <a name="is_directory"></a><a name="is_directory"></a>is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::directory`döndürür. Kalan işlevler `is_directory_file(status(pval))`döndürün.

## <a name="is_empty"></a><a name="is_empty"></a>is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Eğer `is_directory(pval)`, daha `directory_iterator(pval) == directory_iterator()`sonra fonksiyon döner; aksi takdirde `file_size(pval) == 0`döner .

## <a name="is_fifo"></a><a name="is_fifo"></a>is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::fifo`döndürür. Kalan işlevler `is_fifo(status(pval))`döndürün.

## <a name="is_other"></a><a name="is_other"></a>is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::other`döndürür. Kalan işlevler `is_other(status(pval))`döndürün.

## <a name="is_regular_file"></a><a name="is_regular_file"></a>is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::regular`döndürür. Kalan işlevler `is_regular_file(status(pval))`döndürün.

## <a name="is_socket"></a><a name="is_socket"></a>is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::socket`döndürür. Kalan işlevler `is_socket(status(pval))`döndürün.

## <a name="is_symlink"></a><a name="is_symlink"></a>is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::symlink`döndürür. Kalan işlevler `is_symlink(status(pval))`döndürün.

## <a name="last_write_time"></a><a name="last_write_time"></a>last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

İlk iki *işlev, pval*için son veri `file_time_type(-1)` modifikasyonunun saatini veya bir hata oluşursa döndürüler. Son iki *işlev, pval* için son veri değiştirme saatini *new_time.*

## <a name="permissions"></a><a name="permissions"></a>Izin

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

İşlevler *pval* `mask & perms::mask` tarafından seçilen yol adının izinlerini `perms & (perms::add_perms | perms::remove_perms)`. *maske* en fazla ve `perms::add_perms` `perms::remove_perms`içerecektir .

Eğer `mask & perms::add_perms`, işlevler izinleri `status(pval).permissions() | mask & perms::mask`. Aksi takdirde, eğer `mask & perms::remove_perms`, işlevleri `status(pval).permissions() & ~(mask & perms::mask)`izinleri ayarlamak . Aksi takdirde, işlevler izinleri `mask & perms::mask`.

## <a name="proximate"></a><a name="proximate"></a>Yakın

```cpp
path proximate(const path& p, error_code& ec);
path proximate(const path& p, const path& base = current_path());
path proximate(const path& p, const path& base, error_code& ec);
```

## <a name="read_symlink"></a><a name="read_symlink"></a>read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

Fonksiyonlar bir hata `path()` rapor `!is_symlink(pval)`ve eğer döndürün . Aksi takdirde, işlevler sembolik `path` bağlantıyı içeren bir tür nesnesi döndürer.

## <a name="relative"></a><a name="relative"></a>Göreli

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a><a name="remove"></a>Kaldırmak

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

Yalnızca **ve** dosya `exists(symlink_status(pval))` başarıyla kaldırılırsa işlevler doğru döndürülmez. Bir symlink kendisi, seçtiği dosya kaldırılır.

## <a name="remove_all"></a><a name="remove_all"></a>remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

*Pval* bir dizinse, işlevler özyinelemeli olarak tüm dizin girişlerini kaldırır, sonra girişin kendisi. Aksi takdirde, `remove`işlevleri çağrı . Başarıyla kaldırılan tüm öğelerin sayısını döndürerler.

## <a name="rename"></a><a name="rename"></a>Yeni -den adlandırmak

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

İşlevler' den ' *e* *yeniden* ad Bir symlink kendisi, seçtiği dosya değil yeniden adlandırılır.

## <a name="resize_file"></a><a name="resize_file"></a>resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

İşlevler bir dosyanın boyutunu değiştirir,`file_size(pval) == size`

## <a name="space"></a><a name="space"></a>Alanı

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

İşlev *pval*tarafından seçilen hacim hakkında bilgi döndürür , türü `space_info`bir yapıda . Yapı belirlenemeyen herhangi bir değer için içerir. `uintmax_t(-1)`

## <a name="status"></a><a name="status"></a>Durum

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

İşlevler, *pval*ile ilişkili yol adı durumunu, dosya türünü ve izinleri döndürer. Bir symlink kendisi sınanması değil, seçtiği dosya.

## <a name="status_known"></a><a name="status_known"></a>status_known

```cpp
bool status_known(file_status stat) noexcept;
```

İşlev döndürür`stat.type() != file_type::none`

## <a name="swap"></a><a name="swap"></a>Takas

```cpp
void swap(path& left, path& right) noexcept;
```

*İşlev, sol* ve *sağın*içeriğini değiştirir.

## <a name="symlink_status"></a><a name="symlink_status"></a>symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

İşlevler, *pval*ile ilişkili yol adı symlink durumunu, dosya türünü ve izinleri döndürür. İşlevler, seçtiği `status(pval)` dosyayı değil, bir symlink'in kendisi sınanmış olması dışında aynı şekilde çalışır.

## <a name="system_complete"></a><a name="system_complete"></a>system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

İşlevler, gerektiğinde kök adı ile ilişkili geçerli dizindikkate alan mutlak bir yol adı döndürün. \(POSIX için işlevler `absolute(pval)`geri döner.\)

## <a name="temp_directory_path"></a><a name="temp_directory_path"></a>temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

İşlevler, geçici dosyaları içermeye uygun bir dizin için bir yol adı döndürer.

## <a name="u8path"></a><a name="u8path"></a>u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

İlk işlev aynı şekilde çalışır `path(source)` ve ikinci işlev, dosya `path(first, last)` sistemi ne olursa olsun, her durumda seçilen kaynağın UTF-8 olarak kodlanmış bir char öğesi dizisi olarak alınması dışında aynı şekilde çalışır.

## <a name="weakly_canonical"></a><a name="weakly_canonical"></a>weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
