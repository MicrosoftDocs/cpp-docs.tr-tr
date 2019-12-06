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
ms.openlocfilehash: 1ab57a6fc13a03d02963f3d7ecc80f63decb9487
ms.sourcegitcommit: 6ddfb8be5e5923a4d90a2c0f93f76a27ce7ac299
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/06/2019
ms.locfileid: "74898704"
---
# <a name="ltfilesystemgt-functions"></a>&lt;dosya sistemi&gt; işlevleri

[\<filesystem >](../standard-library/filesystem.md) üstbilgisindeki bu ücretsiz işlevler, yollar, dosyalar, symlinks, dizinler ve birimlerde işlemleri değiştirerek ve sorgular. Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi gezintisiC++()](../standard-library/file-system-navigation.md).

## <a name="absolute"></a>salt

```cpp
path absolute(const path& pval, const path& base = current_path());
```

İşlevi, yol adına göre *Pval* öğesine karşılık gelen mutlak yol adını döndürür `base`:

1. `pval.has_root_name() && pval.has_root_directory()` işlev *Pval*döndürürse.

1. `pval.has_root_name() && !pval.has_root_directory()` işlev `pval.root_name()` / `absolute(base).root_directory()` / `absolute(base).relative_path()` / `pval.relative_path()`döndürür.

1. `!pval.has_root_name() && pval.has_root_directory()` işlev `absolute(base).root_name()` / *Pval*' i döndürür.

1. `!pval.has_root_name() && !pval.has_root_directory()` işlev `absolute(base)` / *Pval*' i döndürür.

## <a name="begin"></a>başladı

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Her iki işlev de *iter*döndürüyor.

## <a name="canonical"></a>kurallı

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

All işlevleri, bir mutlak yol adı `pabs = absolute(pval, base)` (veya Base parametresi olmayan aşırı yükleme için `pabs = absolute(pval)`), ardından aşağıdaki adım dizisinde onu kurallı bir biçime küçültün:

1. `is_symlink(X)` **doğru** olan her yol bileşeni `X` `read_symlink(X)`ile değiştirilmiştir.

1. Her yol bileşeni `.` (nokta, önceki yol bileşenleri tarafından belirlenen geçerli dizindir) kaldırılır.

1. Her yol bileşeni çifti /`..` `X`(nokta-nokta, önceki yol bileşenleri tarafından belirlenen üst dizindir) kaldırılır.

İşlev daha sonra `pabs`döndürür.

## <a name="copy"></a>kopya

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

İşlevler muhtemelen, ' deki ' de bir veya daha fazla dosyayı, *OptIn* parametresi olmayan aşırı *yüklemeler için `copy_options::none`* olarak gerçekleştirilen *OptIn*denetimi ' *nden* içine ' ya kopyalayabilir veya bağlar. *OptIn* 'ler en az birini içerir:

- `skip_existing`, `overwrite_existing` veya `update_existing`

- `copy_symlinks` veya `skip_symlinks`

- `directories_only`, `create_symlinks` veya `create_hard_links`

İşlevler ilk *olarak* *, için `f` file_status değerlerini ve için* `t` için belirlenir:

- `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`, `symlink_status` çağırarak

- Aksi takdirde, `status` çağırarak

- Aksi takdirde bir hata bildirin.

`!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`, ardından bir hata bildirir (başka hiçbir şey yapmaz).

Aksi takdirde, `is_symlink(f)`:

- `options & copy_options::skip_symlinks`, hiçbir şey yapmayın.

- Aksi takdirde, `!exists(t)&& options & copy_options::copy_symlinks``copy_symlink(from, to, opts)`.

- Aksi takdirde bir hata bildirin.

Aksi takdirde, `is_regular_file(f)`:

- `opts & copy_options::directories_only`, hiçbir şey yapmayın.

- Aksi takdirde, `opts & copy_options::create_symlinks``create_symlink(to, from)`.

- Aksi takdirde, `opts & copy_options::create_hard_links``create_hard_link(to, from)`.

- Aksi takdirde, `is_directory(f)``copy_file(from, to` / `from.filename(), opts)`.

- Tersi durumda `copy_file(from, to, opts)`.

Aksi takdirde, `is_directory(f) && (opts & copy_options::recursive || !opts)`:

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

Aksi takdirde hiçbir şey yapmayın.

## <a name="copy_file"></a>copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Tüm işlevler muhtemelen ' den ' a ' *dan* ' *a kadar olan* dosyayı, *OptIn* parametresi olmayan aşırı yüklemeler için `copy_options::none` olarak alınmış olan *OptIn*denetimi altına içine Kopyala. *OptIn* 'ler `skip_existing`, `overwrite_existing`veya `update_existing`en çok birini içermelidir.

`exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))`, dosyanın zaten var olduğunu bir hata olarak bildirin.

Aksi takdirde, `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))`*ise dosyanın içeriğini ve özniteliklerini dosyasına kopyalamayı* *deneyin.* Kopyalama girişimi başarısız olursa hata olarak bildirin.

Kopyalama denendiğinde ve başarılı olursa işlevler **true** , değilse **false**döndürür.

## <a name="copy_symlink"></a>copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

`is_directory(from)`, işlev `create_directory_symlink(from, to)`çağırır. Aksi takdirde, `create_symlink(from, to)`çağırır.

## <a name="create_directories"></a>create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

\/b\/c gibi bir yol adı için, işlevi gerektiğinde bir\/Dizin a ve bir\/b oluşturur\/ Yalnızca aslında *Pval*dizinini oluşturduğunda **true** değerini döndürür.

## <a name="create_directory"></a>create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

İşlevi gerektiğinde Dizin *Pval* 'i oluşturur. Bu, yalnızca dizin *Pval*dizinini oluşturduğunda true değerini döndürür; bu durumda, izinleri mevcut dosya *özniteliği*içinden kopyalar ya da *ATTR* parametresi olmayan aşırı yüklemeler için `perms::all` kullanır.

## <a name="create_directory_symlink"></a>create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi *, dizin için*bir oluşturmaksızın olarak bağlantı oluşturur.

## <a name="create_hard_link"></a>create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi, ' *ye*dizin veya dosya için bir sabit bağlantı olarak bağlantı oluşturur.

## <a name="create_symlink"></a>create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi *, dosyanın dosyasına*bir oluşturmaksızın olarak *bağlantı* oluşturur.

## <a name="current_path"></a>current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

*Pval* parametresi olmayan işlevler, geçerli dizinin yol adını döndürür. Kalan işlevler geçerli dizini *Pval*olarak ayarlar.

## <a name="end"></a>erer

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

İlk işlev `directory_iterator()` döndürür ve ikinci işlev `recursive_directory_iterator()` döndürür

## <a name="equivalent"></a>değerinin

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

İşlevler yalnızca *sol* ve *sağ* aynı dosya sistemi varlığını seçtiğinizde **true değerini** döndürür.

## <a name="exists"></a>bulunur

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

İlk işlev `status_known && stat.type() != file_not_found`döndürür. İkinci ve üçüncü işlevleri `exists(status(pval))`döndürür.

## <a name="file_size"></a>file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

İşlevler, `exists(pval) && is_regular_file(pval)` ve dosya boyutu belirlenebileceği şekilde, *Pval*tarafından seçilen dosyanın bayt cinsinden boyutunu döndürür. Aksi takdirde bir hata raporlar ve `uintmax_t(-1)`döndürür.

## <a name="hard_link_count"></a>hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

İşlevi, *Pval*için sabit bağlantı sayısını veya bir hata oluşursa 1 \-1 değerini döndürür.

## <a name="hash_value"></a>hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

İşlev, `pval.native()`için bir karma değer döndürür.

## <a name="is_block_file"></a>is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::block`döndürür. Kalan işlevler `is_block_file(status(pval))`döndürür.

## <a name="is_character_file"></a>is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::character`döndürür. Kalan işlevler `is_character_file(status(pval))`döndürür.

## <a name="is_directory"></a>is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::directory`döndürür. Kalan işlevler `is_directory_file(status(pval))`döndürür.

## <a name="is_empty"></a>is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

`is_directory(pval)`, işlev `directory_iterator(pval) == directory_iterator()`döndürür; Aksi takdirde `file_size(pval) == 0`döndürür.

## <a name="is_fifo"></a>is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::fifo`döndürür. Kalan işlevler `is_fifo(status(pval))`döndürür.

## <a name="is_other"></a>is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::other`döndürür. Kalan işlevler `is_other(status(pval))`döndürür.

## <a name="is_regular_file"></a>is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::regular`döndürür. Kalan işlevler `is_regular_file(status(pval))`döndürür.

## <a name="is_socket"></a>is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::socket`döndürür. Kalan işlevler `is_socket(status(pval))`döndürür.

## <a name="is_symlink"></a>is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

İlk işlev `stat.type() == file_type::symlink`döndürür. Kalan işlevler `is_symlink(status(pval))`döndürür.

## <a name="last_write_time"></a>last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

İlk iki işlev, *Pval*için son veri değişikliği süresini döndürür veya bir hata oluşursa `file_time_type(-1)`. Son iki işlev, *Pval* için son veri değişikliği saatini *new_time*olarak ayarlar.

## <a name="permissions"></a>izinleri

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

İşlevler, *Pval* tarafından seçilen `perms & (perms::add_perms | perms::remove_perms)`denetimi altındaki `mask & perms::mask` için izinleri ayarlar. *maske* `perms::add_perms` ve `perms::remove_perms`en çok birini içermelidir.

`mask & perms::add_perms`, işlevler izinleri `status(pval).permissions() | mask & perms::mask`olarak ayarlar. Aksi takdirde, `mask & perms::remove_perms`işlevler izinleri `status(pval).permissions() & ~(mask & perms::mask)`olarak ayarlar. Aksi takdirde, işlevleri `mask & perms::mask`izinlerini ayarlar.

## <a name="proximate"></a>Yakındaki

```cpp
path proximate(const path& p, error_code& ec);
path proximate(const path& p, const path& base = current_path());
path proximate(const path& p, const path& base, error_code& ec);
```

## <a name="read_symlink"></a>read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

İşlevler bir hata bildirir ve `!is_symlink(pval)``path()` döndürür. Aksi takdirde, işlevler sembolik bağlantıyı içeren `path` türünde bir nesne döndürür.

## <a name="relative"></a>konumuyla

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a>temizlenmesine

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

İşlevler yalnızca `exists(symlink_status(pval))` ve dosya başarıyla kaldırılmışsa **true değerini** döndürür. Bir oluşturmaksızın, seçtiği dosya değil, kendisi tarafından kaldırılır.

## <a name="remove_all"></a>remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

*Pval* bir dizin ise, işlevler yinelemeli olarak tüm dizin girdilerini kaldırır ve sonra girişin kendisidir. Aksi takdirde, işlevleri `remove`çağırır. Başarılı bir şekilde kaldırılan tüm öğe sayısını döndürür.

## <a name="rename"></a>Yeniden Adlandır

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

İşlevleri ' *den* *' ye yeniden adlandırır.* Oluşturmaksızın, seçtiği dosya değil, kendi yeniden adlandırılacaktır.

## <a name="resize_file"></a>resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

İşlevler, `file_size(pval) == size` gibi bir dosyanın boyutunu değiştirir

## <a name="space"></a>boşlu

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

İşlevi, `space_info`türünde bir yapıda *Pval*tarafından seçilen birimle ilgili bilgileri döndürür. Yapı, belirlenemediği herhangi bir değer için `uintmax_t(-1)` içerir.

## <a name="status"></a>durumlarına

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

İşlevler, yol adını, dosya türünü ve izinleri *Pval*ile ilişkili olarak döndürür. Oluşturmaksızın, kendisini test etmez, ancak seçtiği dosya.

## <a name="status_known"></a>status_known

```cpp
bool status_known(file_status stat) noexcept;
```

İşlev `stat.type() != file_type::none` döndürür

## <a name="swap"></a>Kur

```cpp
void swap(path& left, path& right) noexcept;
```

İşlevi, *sol* ve *sağ*içeriğini değiş tokuş eder.

## <a name="symlink_status"></a>symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

İşlevler, *Pval*ile ilişkili olan oluşturmaksızın durum yolunu, dosya türünü ve izinleri döndürür. İşlevler, bir oluşturmaksızın 'in seçtiği dosyanın kendisi değil, kendisini `status(pval)` benzer şekilde davranır.

## <a name="system_complete"></a>system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

İşlevler, gerekli olduğu gibi, kök adıyla ilişkili geçerli dizini de hesaba alan mutlak bir yol adı döndürür. POSIX Için \(, işlevler `absolute(pval)`döndürür.\)

## <a name="temp_directory_path"></a>temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

İşlevler, geçici dosyaları içerecek şekilde uygun bir dizin için bir yol adı döndürür.

## <a name="u8path"></a>u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

İlk işlev `path(source)` ile aynı şekilde davranır ve ikinci işlev, her durumda seçilen kaynağın, dosya sisteminden bağımsız olarak UTF-8 olarak kodlanmış Char öğelerinin bir dizisi olarak alınması dışında `path(first, last)` aynı şekilde davranır.

## <a name="weakly_canonical"></a>weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
