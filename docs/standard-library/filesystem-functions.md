---
title: '&lt;dosya sistemi&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
ms.assetid: be3cb821-4728-4d47-ab78-858fa8aa5045
author: corob-msft
ms.author: corob
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
ms.workload:
- cplusplus
ms.openlocfilehash: 0e47339813256d189e1ce6b71506d9ae29a93f51
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213471"
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
|[last_write_time](#last_write_time)|[İzinleri](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[Yeniden adlandırma](#rename)|
|[resize_file](#resize_file)|[alanı](#space)|[Durumu](#status)|
|[status_known](#status_known)|[değiştirme](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|


## <a name="absolute"></a> Mutlak

```cpp
path absolute(const path& pval, const path& base = current_path());
```

İşlev, karşılık gelen mutlak yol adını döndürür. `pval` göreli yol adını `base`:

1. Varsa pval.has_root_name() & & pval pval.has_root_directory() işlevi döndürür.

1. Varsa pval.has_root_name() & &! pval.has_root_directory() işlevi pval.root_name() döndürür / absolute(base).root_directory() / absolute(base).relative_path() / pval.relative_path().

1. Varsa! pval.has_root_name() & & pval.has_root_directory() işlevi absolute(base).root_name() döndürür / pval.

1. Varsa! pval.has_root_name() & &! pval.has_root_directory() işlevi absolute(base) döndürür / pval.

## <a name="begin"></a>  başlayın

```cpp
const directory_iterator& begin(const directory_iterator& iter) noexcept;
const recursive_directory_iterator&
    begin(const recursive_directory_iterator& iter) noexcept;
```

Her iki işlev dönüş `iter`.

## <a name="canonical"></a>  Canonical

```cpp
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```

Tüm İşlevler bir mutlak yol pabs form mutlak (pval, temel) = (veya pabs = absolute(pval) temel parametre olmadan aşırı yüklemesi için), ardından adımları aşağıdaki sırayla kurallı bir form azaltın:

1. Her yol bileşenini X read_symlink(X) tarafından hangi is_symlink(X) doğrudur almıştır.

1. Her bir yol bileşeni. (nokta geçerli önceki yol bileşenleri tarafından belirlenen geçerli dizin) kaldırılır.

1. Her yol bileşenleri X çiftinin /... (nokta nokta geçerli önceki yol bileşenleri tarafından oluşturulan bir üst dizin) kaldırılır.

İşlev, ardından pabs döndürür.

## <a name="copy"></a>  kopyalama

```cpp
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;
```

İşlevler büyük olasılıkla tüm kopyalayın veya bir veya daha fazla dosyaları bağlantısını `from` için `to` denetiminde `opts`, olmadan aşırı yüklemeler için copy_options::none olarak gerçekleştirilen `opts` parametresi. `opts` en fazla birini içeren:

- skip_existing, overwrite_existing veya update_existing

- copy_symlinks veya skip_symlinks

- directories_only, create_symlinks veya create_hard_links

İşlevler için file_status değerleri f ilk belirlemek `from` ve t için `to`:

- varsa bölgedeyse & (copy_options::create_symlinks &#124; copy_options::skip_symlinks) tarafından symlink_status çağırma

- Aksi takdirde, durum çağırarak

- Aksi takdirde bir hata rapor.

Varsa! exists(f) &#124; &#124; (f, t) eşdeğer &#124; &#124; is_other(f) &#124; &#124; is_other(t) &#124; &#124; is_directory(f) & & is_regular_file(t), bunlar daha sonra bir hata rapor (ve başka hiçbir şey yapma).

Aksi halde, ardından is_symlink(f):

- Seçenekler & copy_options::skip_symlinks ardından yapmamanız durumunda.

- Aksi takdirde! exists(t) & & Seçenekleri & copy_options::copy_symlinks sonra copy_symlink (gelen, için kabul eder).

- Aksi takdirde bir hata rapor.

Aksi halde, ardından is_regular_file(f):

- Varsa bölgedeyse & copy_options::directories_only ardından yapın hiçbir şey.

- Aksi takdirde bölgedeyse & ardından copy_options::create_symlinks create_symlink(to, from).

- Aksi takdirde bölgedeyse & ardından copy_options::create_hard_links create_hard_link(to, from).

- Aksi takdirde is_directory(f) sonra copy_file (, çok/from.filename(), kabul eder).

- Aksi takdirde copy_file (gelen, için kabul eder).

Aksi takdirde is_directory(f) & & (bölgedeyse & copy_options::recursive &#124; &#124; ! kabul eder) sonra:

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

İşlevler, tüm büyük olasılıkla dosyayı Kopyala `from` için `to` denetiminde `opts`, olmadan aşırı yüklemeler için copy_options::none olarak gerçekleştirilen `opts` parametresi. `opts` en fazla bir skip_existing, overwrite_existing veya update_existing içeren.

Varsa mevcut\(için\) && \!\(bölgedeyse & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options::update_existing\) \) sonra rapor dosyası zaten var. bir hata olarak.

Aksi takdirde \!var.\(için\) &#124; &#124; bölgedeyse & copy_options::overwrite_existing &#124; &#124; bölgedeyse & copy_options::update_existing & & last_write_time\(için \) \< last_write_time\(gelen\) &#124; &#124; \! \(bölgedeyse & \(copy_options::skip_existing &#124; copy_options::o verwrite_existing &#124; copy_options:update_existing\) \) dosyasına dosyasından öznitelikleri ve içeriği kopyalama girişimi. Kopyalama girişimi başarısız olursa hata olarak bildirin.

İşlevleri doğru kopyalama denenir ve başarılı olur, aksi takdirde false döndürün.

## <a name="copy_symlink "></a>  copy_symlink

```cpp
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;
```

Varsa is_directory\(gelen\) create_directory_symlink işlevi çağıran\(gelen,\). İse create_symlink çağırır\(gelen,\).

## <a name="create_directories"></a>  create_directories

```cpp
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;
```

Gibi bir yol için bir\/b\/c işlevi dizin oluşturur bir ve\/dizini oluşturabilmesi gereken şekilde b bir\/b\/gerektiğinde c. Yalnızca gerçekten dizini oluşturur, true döndürür `pval`.

## <a name="create_directory"></a>  create_directory

```cpp
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;
```

İşlev dizini `pval` gerektiğinde. Yalnızca gerçekten dizini oluşturur, true döndürür `pval`, bu durumda varolan dosyanın izinlerini kopyalar `attr`, veya olmadan aşırı perms::all kullanımları `attr` parametresi.

## <a name="create_directory_symlink "></a>  create_directory_symlink

```cpp
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi bağlantı olarak dizine bir sembolik bağlantısını oluşturur. `to`.

## <a name="create_hard_link"></a>  create_hard_link

```cpp
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;
```

İşlevi, dizin veya dosya için sabit bir bağlantı olarak bağlantısını oluşturur. `to`.

## <a name="create_symlink "></a>  create_symlink

```cpp
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;
```

Bir işlev oluşturur `link` dosyasına bir sembolik bağlantısını olarak `to`.

## <a name="current_path"></a>  current_path

```cpp
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;
```

Hiçbir parametre işlevleriyle `pval` geçerli dizin için yol adını döndürür. Geçerli dizin kalan işlevleri kümesine `pval`.

## <a name="end"></a>  Son

```cpp
directory_iterator& end(const directory_iterator& iter) noexcept;
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;
```

İlk işlev directory_iterator döndürür\( \) ve ikinci işlev recursive_directory_iterator döndürür\(\)

## <a name="equivalent"></a>  eşdeğeri

```cpp
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;
```

İşlevler yalnızca, true döndürür `left` ve `right` aynı dosya sistemi varlık belirleyin.

## <a name="exists"></a>  Var.

```cpp
bool exists(file_status stat) noexcept;
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;
```

İlk işlev status_known döndürür & & stat.type\( \) \! \= file_not_found. İkinci ve üçüncü oluşturucular dönüş var.\(durumu\(pval\)\).

## <a name="file_size"></a>  file_size

```cpp
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;
```

İşlevler tarafından belirtilen dosyanın bayt cinsinden boyutu döndürür. `pval`, varsa var\(pval\) & & is_regular_file\(pval\) ve dosya boyutu belirlenebilir. Aksi takdirde, bir hata ve dönüş uintmax_t rapor\(\-1\).

## <a name="hard_link_count"></a>  hard_link_count

```cpp
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;
```

İşlev için sabit bağlantılar verir `pval`, veya \-bir hata oluşursa 1.

## <a name="hash_value"></a>  hash_value

```cpp
size_t hash_value(const path& pval) noexcept;
```

İşlev pval.native için bir karma değer döndürür\(\).

## <a name="is_block_file"></a>  is_block_file

```cpp
bool is_block_file(file_status stat) noexcept;
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::block. Kalan işlevler is_block_file döndürür\(durumu\(pval\)\).

## <a name="is_character_file"></a>  is_character_file

```cpp
bool is_character_file(file_status stat) noexcept;
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::character. Kalan işlevler is_character_file döndürür\(durumu\(pval\)\).

## <a name="is_directory "></a>  is_directory

```cpp
bool is_directory(file_status stat) noexcept;
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::directory. Kalan işlevler is_directory_file döndürür\(durumu\(pval\)\).

## <a name="is_empty"></a>  is_empty

```cpp
bool is_empty(file_status stat) noexcept;
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;
```

Varsa is_directory\(pval\) directory_iterator işlevi döndürür sonra\(pval\) \= \= directory_iterator\(\); Aksi halde file_ döndürür boyutu\(pval\) \= \= 0.

## <a name="is_fifo"></a>  is_fifo

```cpp
bool is_fifo(file_status stat) noexcept;
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::fifo. Kalan işlevler is_fifo döndürür\(durumu\(pval\)\).

## <a name="is_other"></a>  is_other

```cpp
bool is_other(file_status stat) noexcept;
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::other. Kalan işlevler is_other döndürür\(durumu\(pval\)\).

## <a name="s_regular_file"></a>  is_regular_file

```cpp
bool is_regular_file(file_status stat) noexcept;
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::regular. Kalan işlevler is_regular_file döndürür\(durumu\(pval\)\).

## <a name="is_socket"></a>  is_socket

```cpp
bool is_socket(file_status stat) noexcept;
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::socket. Kalan işlevler is_socket döndürür\(durumu\(pval\)\).

## <a name="is_symlink"></a>  is_symlink

```cpp
bool is_symlink(file_status stat) noexcept;
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;
```

İlk işlev stat.type döndürür\( \) \= \= file_type::symlink. Kalan işlevler is_symlink döndürür\(durumu\(pval\)\).

## <a name="last_write_time"></a>  last_write_time

```cpp
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;
```

İlk iki işlevler için son veri değişikliği zamanı döndürür `pval`, veya file_time_type\(\-1\) hata oluşması durumunda. Son iki işlev için son veri değiştirilme saatini ayarlayın `pval` new_time için.

## <a name="permissions"></a>  İzinleri

```cpp
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;
```

İşlevler tarafından belirtilen yol için izinler `pval` maskesi & perms::mask izinleri denetiminde & \(perms::add_perms &#124; perms::remove_perms\). Maske en fazla bir perms::add_perms ve perms::remove_perms içeren.

Maske & perms::add_perms işlevleri durumuna izinleri varsa\(pval\).permissions\( \) &#124; maskesi & perms::mask. Aksi takdirde maskesi & perms::remove_perms işlevleri izinleri durumuna ayarlarsanız\(pval\).permissions\( \) & ~\(maskesi & perms::mask\). Aksi takdirde, İşlevler için maske & perms::mask izinlerini ayarlayın.

## <a name="read_symlink"></a>  read_symlink

```cpp
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```

İşlevler bir hata ve dönüş yolu rapor\( \) varsa \!is_symlink\(pval\). Aksi takdirde, İşlevler türünde bir nesne döndürür `path` sembolik bağlantısını içeren.

## <a name="remove"></a>  Kaldır

```cpp
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;
```

İşlevler var. yalnızca gerekirse true döndürür\(symlink_status\(pval\) \) ve dosyayı başarıyla kaldırıldı. Bir sembolik bağlantısını kendisi kaldırıldıysa, onu atayan dosyası değil değildir.

## <a name="remove_all"></a>  remove_all

```cpp
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;
```

Varsa `pval` bir dizin işlevleri yinelemeli olarak tüm dizin girdisi, ardından giriş kaldırın. Aksi takdirde kaldırma işlevlerini çağırın. Bunlar, başarıyla kaldırılan tüm öğelerin sayısını döndürür.

## <a name="rename"></a>  Yeniden adlandırma

```cpp
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;
```

İşlevleri Yeniden Adlandır `from` için `to`. Bir sembolik bağlantısını kendisi yeniden adlandırılmış, atayan dosyası değil değildir.

## <a name="resize_file"></a>  resize_file

```cpp
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;
```

Böyle bir dosyanın boyutunu işlevleri alter bu file_size\(pval\) \= \= boyutu

## <a name="space"></a>  alanı

```cpp
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;
```

İşlev tarafından belirlenen birim hakkındaki bilgileri döndürür `pval`, bir yapı türü `space_info`. Yapı uintmax_t içerdiği\(\-1\) için herhangi bir değer belirlenemiyor.

## <a name="status"></a>  Durumu

```cpp
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;
```

İşlevler pathname durum, dosya türü ve ilişkili izinler döndürür `pval`. Kendi test hedefine sembolik bağlantı olduğu halde bu dosyayı belirtir.

## <a name="status_known"></a>  status_known

```cpp
bool status_known(file_status stat) noexcept;
```

İşlev stat.type döndürür\( \) \! \= file_type::none

## <a name="swap"></a>  değiştirme

```cpp
void swap(path& left, path& right) noexcept;
```

İşlev içeriğini birbiriyle değiştirir `left` ve `right`.

## <a name="symlink_status"></a>  symlink_status

```cpp
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;
```

İşlevler pathname hedefine sembolik bağlantı durumunu, dosya türü ve ilişkili izinler döndürür `pval`. İşlevler durumu olarak aynı şekilde davranır\(pval\) dosyası değil, kendi test hedefine sembolik bağlantı olması dışında, belirler.

## <a name="system_complete"></a>  system_complete

```cpp
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```

İşlevler, kök adıyla ilişkili geçerli dizini gerekli olarak dikkate alan bir mutlak bir yol adı döndürür. \(İşlevler, POSIX mutlak döndürür\(pval\).\)

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

İlk işlev path(source) gibi davranır ve ikinci işlevi yolu gibi davranır (ilk olarak, son) dışında her durumda belirtilen kaynak dosya bağımsız olarak UTF-8 kodlanmış karakter öğeleri dizisi olarak alınır.


