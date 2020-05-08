---
title: '&lt;Dosya&gt; sistemi işlevleri'
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
ms.openlocfilehash: 1e5994faab69c1809f820b41186d9b618aa7c193
ms.sourcegitcommit: d2ccbba1bf4e66d6b6b0582dc01ba39f4a54f0aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2020
ms.locfileid: "82984090"
---
# <a name="ltfilesystemgt-functions"></a>&lt;Dosya&gt; sistemi işlevleri

Dosya sistemi>üst bilgisindeki Bu ücretsiz işlevler, yollar, dosyalar, symbağlantılar, dizinler ve birimlerde işlemleri değiştirerek ve sorgular. [ \<](../standard-library/filesystem.md) Daha fazla bilgi ve kod örneği için bkz. [dosya sistemi Gezintisi (C++)](../standard-library/file-system-navigation.md).

## <a name="absolute"></a><a name="absolute"></a>salt

```cpp
path absolute(const path& pval, const path& base = current_path());
```

İşlevi, yol adına `base`göre *Pval* öğesine karşılık gelen mutlak yol adını döndürür:

1. `pval.has_root_name() && pval.has_root_directory()` İşlev *Pval*döndürürse.

1. `pval.has_root_name() && !pval.has_root_directory()` İşlev `pval.root_name()`  / döndürürse `absolute(base).root_directory()`.  /  `absolute(base).relative_path()`  /  `pval.relative_path()`

1. `!pval.has_root_name() && pval.has_root_directory()` İşlev `absolute(base).root_name()`  /  *Pval*döndürürse.

1. `!pval.has_root_name() && !pval.has_root_directory()` İşlev `absolute(base)`  /  *Pval*döndürürse.

## <a name="begin"></a><a name="begin"></a>başladı

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Her iki işlev de *iter*döndürüyor.

## <a name="canonical"></a><a name="canonical"></a>kurallı

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

İşlevlerin hepsi, mutlak bir yol adı `pabs = absolute(pval, base)` oluşturur ( `pabs = absolute(pval)` veya Base parametresi olmayan aşırı yükleme için), ardından aşağıdaki adım dizisinde onu kurallı bir biçime küçültün:

1. **True** olan `is_symlink(X)` her `X` yol bileşeni, ile `read_symlink(X)`değiştirilmiştir.

1. Her yol bileşeni `.` (nokta, önceki yol bileşenleri tarafından belirlenen geçerli dizindir) kaldırılır.

1. Her yol bileşeni `X` / `..` çifti (nokta-nokta, önceki yol bileşenleri tarafından belirlenen üst dizindir) kaldırılır.

Sonra işlev döndürür `pabs`.

## <a name="copy"></a><a name="copy"></a>kopya

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

İşlevler muhtemelen, *' deki ' de bir* veya daha fazla dosyayı, hiçbir *OptIn* parametresi olmayan aşırı yüklemeler için olarak `copy_options::none` gerçekleştirilen *OptIn* *denetimi altına '* a kopyalayabilir veya bağlar. *OptIn* 'ler en az birini içerir:

- `skip_existing`, `overwrite_existing`, veya`update_existing`

- `copy_symlinks` veya `skip_symlinks`

- `directories_only`, `create_symlinks`, veya`create_hard_links`

İşlevler `f` *önce ve* `t` için için file_status değerlerini *belirlenir:*

- `opts & (copy_options::create_symlinks | copy_options::skip_symlinks)`şunu çağırarak`symlink_status`

- Aksi takdirde, çağırarak`status`

- Aksi takdirde bir hata bildirin.

`!exists(f) || equivalent(f, t) || is_other(f) || is_other(t) || is_directory(f)&& is_regular_file(t)`Daha sonra bir hata bildirir (ve başka hiçbir şey yapmaz).

`is_symlink(f)` Aksi takdirde:

- Varsa `options & copy_options::skip_symlinks`, hiçbir şey yapmayın.

- Aksi takdirde, `!exists(t)&& options & copy_options::copy_symlinks`,, `copy_symlink(from, to, opts)`ve.

- Aksi takdirde bir hata bildirin.

`is_regular_file(f)`Aksi takdirde, daha sonra:

- Varsa `opts & copy_options::directories_only`, hiçbir şey yapmayın.

- Aksi takdirde, `opts & copy_options::create_symlinks`,, `create_symlink(to, from)`ve.

- Aksi takdirde, `opts & copy_options::create_hard_links`,, `create_hard_link(to, from)`ve.

- Aksi takdirde, `is_directory(f)`,, `copy_file(from, to`  /  `from.filename(), opts)`ve.

- Tersi durumda `copy_file(from, to, opts)`.

`is_directory(f) && (opts & copy_options::recursive || !opts)`Aksi takdirde, daha sonra:

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

## <a name="copy_file"></a><a name="copy_file"></a>copy_file

```cpp
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

Tüm işlevler muhtemelen ' den ' a ' *dan* ' *a kadar olan* dosyayı, *OptIn* parametresi olmayan aşırı yüklemeler `copy_options::none` için olarak alınan *OptIn*denetimi altına içine Kopyala. *OptIn* 'ler `skip_existing`, `overwrite_existing`, veya `update_existing`' den en çok birini içermelidir.

İse `exists(to) && !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options::update_existing))`, dosyanın zaten var olduğunu bir hata olarak bildirin.

Aksi takdirde, `!exists(to) || opts & copy_options::overwrite_existing || opts & copy_options::update_existing&& last_write_time(to) < last_write_time(from) || !(opts & (copy_options::skip_existing | copy_options::overwrite_existing | copy_options:update_existing))`, ' *den* dosyasına içeriğini ve özniteliklerini dosyasına kopyalamayı *deneyin.* Kopyalama girişimi başarısız olursa hata olarak bildirin.

Kopyalama denendiğinde ve başarılı olursa işlevler **true** , değilse **false**döndürür.

## <a name="copy_symlink"></a><a name="copy_symlink"></a>copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

İse `is_directory(from)`, işlev çağırır `create_directory_symlink(from, to)`. Aksi takdirde, çağırır `create_symlink(from, to)`.

## <a name="create_directories"></a><a name="create_directories"></a>create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

\/B\/c gibi bir yol adı için, işlev gerektiği şekilde a ve\/b dizinini oluşturur, böylece Dizin bir\/b\/c 'yi gerektiği şekilde oluşturabilir. Yalnızca aslında *Pval*dizinini oluşturduğunda **true** değerini döndürür.

## <a name="create_directory"></a><a name="create_directory"></a>create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

İşlevi gerektiğinde Dizin *Pval* 'i oluşturur. Yalnızca gerçekte Dizin *Pval*'yi oluşturuyorsa, bu, var olan dosya *özniteliği*içindeki izinleri kopyalayan ya da `perms::all` *ATTR* parametresi olmayan aşırı yüklemeler için kullandığı durumlarda true değerini döndürür.

## <a name="create_directory_symlink"></a><a name="create_directory_symlink"></a>create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi *, dizin için*bir oluşturmaksızın olarak bağlantı oluşturur.

## <a name="create_hard_link"></a><a name="create_hard_link"></a>create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi, ' *ye*dizin veya dosya için bir sabit bağlantı olarak bağlantı oluşturur.

## <a name="create_symlink"></a><a name="create_symlink"></a>create_symlink

```cpp
void create_symlink(const path& to, const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi *, dosyanın dosyasına*bir oluşturmaksızın olarak *bağlantı* oluşturur.

## <a name="current_path"></a><a name="current_path"></a>current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

*Pval* parametresi olmayan işlevler, geçerli dizinin yol adını döndürür. Kalan işlevler geçerli dizini *Pval*olarak ayarlar.

## <a name="end"></a><a name="end"></a>erer

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

İlk işlev döner `directory_iterator()` ve ikinci işlev döndürür`recursive_directory_iterator()`

## <a name="equivalent"></a><a name="equivalent"></a>değerinin

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

İşlevler yalnızca *sol* ve *sağ* aynı dosya sistemi varlığını seçtiğinizde **true değerini** döndürür.

## <a name="exists"></a><a name="exists"></a>bulunur

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `status_known && stat.type() != file_not_found`. İkinci ve üçüncü işlevleri döndürülür `exists(status(pval))`.

## <a name="file_size"></a><a name="file_size"></a>file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

İşlevler, boyutu *Pval*tarafından seçilen dosyanın bayt cinsinden değerini döndürür `exists(pval) && is_regular_file(pval)` ve dosya boyutu belirlenebilir. Aksi takdirde bir hata bildirir ve döndürür `uintmax_t(-1)`.

## <a name="hard_link_count"></a><a name="hard_link_count"></a>hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

İşlevi, *Pval*için sabit bağlantı sayısını veya \-bir hata oluşursa 1 değerini döndürür.

## <a name="hash_value"></a><a name="hash_value"></a>hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

İşlevi için `pval.native()`bir karma değer döndürür.

## <a name="is_block_file"></a><a name="is_block_file"></a>is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::block`. Kalan işlevler döndürülür `is_block_file(status(pval))`.

## <a name="is_character_file"></a><a name="is_character_file"></a>is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::character`. Kalan işlevler döndürülür `is_character_file(status(pval))`.

## <a name="is_directory"></a><a name="is_directory"></a>is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::directory`. Kalan işlevler döndürülür `is_directory_file(status(pval))`.

## <a name="is_empty"></a><a name="is_empty"></a>is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Varsa `is_directory(pval)`, işlev döndürür `directory_iterator(pval) == directory_iterator()`; Aksi takdirde, `file_size(pval) == 0`döndürür.

## <a name="is_fifo"></a><a name="is_fifo"></a>is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::fifo`. Kalan işlevler döndürülür `is_fifo(status(pval))`.

## <a name="is_other"></a><a name="is_other"></a>is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::other`. Kalan işlevler döndürülür `is_other(status(pval))`.

## <a name="is_regular_file"></a><a name="is_regular_file"></a>is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::regular`. Kalan işlevler döndürülür `is_regular_file(status(pval))`.

## <a name="is_socket"></a><a name="is_socket"></a>is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::socket`. Kalan işlevler döndürülür `is_socket(status(pval))`.

## <a name="is_symlink"></a><a name="is_symlink"></a>is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

İlk işlev döndürür `stat.type() == file_type::symlink`. Kalan işlevler döndürülür `is_symlink(status(pval))`.

## <a name="last_write_time"></a><a name="last_write_time"></a>last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

İlk iki işlev, *Pval*için son veri değişikliği süresini veya `file_time_type(-1)` bir hata oluşursa döndürür. Son iki işlev, *Pval* için son veri değişikliği saatini *new_time*olarak ayarlar.

## <a name="permissions"></a><a name="permissions"></a>izinleri

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

İşlevleri *Pval* tarafından seçilen ve denetimi `mask & perms::mask` altında olan `perms & (perms::add_perms | perms::remove_perms)`yol için izinleri ayarlar. *maske* , ve ' `perms::add_perms` `perms::remove_perms`nin en çok birini içermelidir.

İse `mask & perms::add_perms`, işlevleri izinleri olarak `status(pval).permissions() | mask & perms::mask`ayarlar. `mask & perms::remove_perms`Aksi takdirde, işlevleri izinleri olarak `status(pval).permissions() & ~(mask & perms::mask)`ayarlar. Aksi takdirde, işlevleri izinleri olarak `mask & perms::mask`ayarlar.

## <a name="proximate"></a><a name="proximate"></a>Yakındaki

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

İşlevler bir hata bildirir ve bunu döndürür `path()` `!is_symlink(pval)`. Aksi takdirde, işlevler sembolik bağlantıyı içeren türünde `path` bir nesne döndürür.

## <a name="relative"></a><a name="relative"></a>konumuyla

```cpp
path relative(const path& p, error_code& ec);
path relative(const path& p, const path& base = current_path());
path relative(const path& p, const path& base, error_code& ec);
```

## <a name="remove"></a><a name="remove"></a>temizlenmesine

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

İşlevler yalnızca `exists(symlink_status(pval))` ve dosya başarıyla kaldırılmışsa **true değerini** döndürür. Bir oluşturmaksızın, seçtiği dosya değil, kendisi tarafından kaldırılır.

## <a name="remove_all"></a><a name="remove_all"></a>remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

*Pval* bir dizin ise, işlevler yinelemeli olarak tüm dizin girdilerini kaldırır ve sonra girişin kendisidir. Aksi takdirde, işlevleri çağırır `remove`. Başarılı bir şekilde kaldırılan tüm öğe sayısını döndürür.

## <a name="rename"></a><a name="rename"></a>Yeniden Adlandır

```cpp
void rename(const path& from, const path& to);
void rename(const path& from, const path& to, error_code& ec) noexcept;
```

İşlevleri ' *den* *' ye yeniden adlandırır.* Oluşturmaksızın, seçtiği dosya değil, kendi yeniden adlandırılacaktır.

## <a name="resize_file"></a><a name="resize_file"></a>resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

İşlevler, bir dosyanın boyutunu şu şekilde değiştirir`file_size(pval) == size`

## <a name="space"></a><a name="space"></a>boşlu

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

İşlevi, *Pval*tarafından seçilen birim hakkındaki bilgileri, türü `space_info`bir yapıda döndürür. Yapı, belirlenemediği herhangi bir değer için içerir `uintmax_t(-1)` .

## <a name="status"></a><a name="status"></a>durumlarına

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

İşlevler, yol adını, dosya türünü ve izinleri *Pval*ile ilişkili olarak döndürür. Oluşturmaksızın, kendisini test etmez, ancak seçtiği dosya.

## <a name="status_known"></a><a name="status_known"></a>status_known

```cpp
bool status_known(file_status stat) noexcept;
```

İşlev döndürür`stat.type() != file_type::none`

## <a name="swap"></a><a name="swap"></a>Kur

```cpp
void swap(path& left, path& right) noexcept;
```

İşlevi, *sol* ve *sağ*içeriğini değiş tokuş eder.

## <a name="symlink_status"></a><a name="symlink_status"></a>symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, error_code& ec) noexcept;
```

İşlevler, *Pval*ile ilişkili olan oluşturmaksızın durum yolunu, dosya türünü ve izinleri döndürür. İşlevler, bir oluşturmaksızın 'in `status(pval)` seçtiği dosya değil, kendisini test ettiği gibi davranır.

## <a name="system_complete"></a><a name="system_complete"></a>system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

İşlevler, gerekli olduğu gibi, kök adıyla ilişkili geçerli dizini de hesaba alan mutlak bir yol adı döndürür. \(POSIX için işlevler döndürülür `absolute(pval)`.\)

## <a name="temp_directory_path"></a><a name="temp_directory_path"></a>temp_directory_path

```cpp
path temp_directory_path();
path temp_directory_path(error_code& ec);
```

İşlevler, geçici dosyaları içerecek şekilde uygun bir dizin için bir yol adı döndürür.

## <a name="u8path"></a><a name="u8path"></a>u8path

```cpp
template <class Source>
path u8path(const Source& source);

template <class InIt>
path u8path(InIt first, InIt last);
```

İlk işlev ile aynı şekilde `path(source)` davranır ve ikinci işlev aynı şekilde, her durumda seçilen `path(first, last)` kaynağın her durumda, dosya sistemine göre UTF-8 olarak kodlanmış Char öğelerinin bir dizisi olarak alınması dışında davranır.

## <a name="weakly_canonical"></a><a name="weakly_canonical"></a>weakly_canonical

```cpp
path weakly_canonical(const path& p);
path weakly_canonical(const path& p, error_code& ec);
```
