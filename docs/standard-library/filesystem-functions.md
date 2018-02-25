---
title: "&lt;dosya sistemi&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
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
ms.openlocfilehash: 3c3fd7eabba97ff7e32cad06ad1d5460f94b329d
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltfilesystemgt-functions"></a>&lt;dosya sistemi&gt; işlevleri
Bu ücretsiz işlevlerde [ \<dosya sistemi >](../standard-library/filesystem.md) üstbilgi yolları, dosyaları, simgesel bağlantı, dizinler ve birimler değiştirme ve sorgu işlemi gerçekleştirir. Daha fazla bilgi ve kod örnekleri için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).  
||||  
|-|-|-|  
|[absolute](#absolute)|[Başlangıç](#begin)|[Kurallı](#canonical)|
|[Kopyalama](#copy)|[copy_file](#copy_file)|[copy_symlink](#copy_symlink)|
|[create_directories](#create_directories)|[create_directory](#create_directory)|[create_directory_symlink](#create_directory_symlink)|
|[create_hard_link](#create_hard_link)|[create_symlink](#create_symlink)|[current_path](#current_path)|
|[Bitiş](#end)|[eşdeğer](#equivalent)|[var](#exists)|
|[file_size](#file_size)|[hard_link_count](#hard_link_count)|[hash_value](#hash_value)|
|[is_block_file](#is_block_file)|[is_character_file](#is_character_file)|[is_directory](#is_directory)|
|[is_empty](#is_empty)|[is_fifo](#is_fifo)|[is_other](#is_other)|
|[is_regular_file](#is_regular_file)|[is_socket](#is_socket)|[is_symlink](#is_symlink)|
|[last_write_time](#last_write_time)|[İzinleri](#permissions)|[read_symlink](#read_symlink)|
|[remove](#remove)|[remove_all](#remove_all)|[Yeniden Adlandır](#rename)|
|[resize_file](#resize_file)|[Alanı](#space)|[Durumu](#status)|
|[status_known](#status_known)|[Değiştirme](#swap)|[symlink_status](#symlink_status)|
|[system_complete](#system_complete)|[temp_directory_path](#temp_directory_path)|[u8path](#u8path)|  


## <a name=""></a>  <a name="absolute"></a> Mutlak  
  
```  
path absolute(const path& pval, const path& base = current_path());
```  
  
 İşlevi karşılık gelen mutlak bir yol adı döndürür `pval` göreli yol `base`:  
  
1.  Varsa pval.has_root_name() & & pval.has_root_directory() işlevi pval döndürür.  
  
2.  Varsa pval.has_root_name() & &! pval.has_root_directory() işlevi döndürür pval.root_name() / absolute(base).root_directory() / absolute(base).relative_path() / pval.relative_path().  
  
3.  Varsa! pval.has_root_name() & & pval.has_root_directory() işlevi döndürür absolute(base).root_name() / pval.  
  
4.  Varsa! pval.has_root_name() & &! pval.has_root_directory() işlevi döndürür absolute(base) / pval.  
  
## <a name="begin">Başlangıç</a>  
  
```  
const directory_iterator& begin(const directory_iterator& iter) noexcept;  
const recursive_directory_iterator& 
    begin(const recursive_directory_iterator& iter) noexcept;  
```  
  
 Her iki işlevi dönüş `iter`.  
  
## <a name="canonical">Kurallı</a>  
  
```  
path canonical(const path& pval, const path& base = current_path());
path canonical(const path& pval, error_code& ec);
path canonical(const path& pval, const path& base, error_code& ec);
```  
  
 Tüm işlevleri bir mutlak yol pabs form mutlak (pval, temel) = (veya pabs temel parametre ile aşırı absolute(pval) =), kurallı forma adımları aşağıdaki sırayla azaltmak:  
  
1.  Her bir yol bileşeni X hangi is_symlink(X) doğrudur tarafından read_symlink(X) yerini almıştır.  
  
2.  Her yol bileşeni. (nokta önceki yol bileşenleri tarafından belirlenen geçerli dizin olduğu) kaldırılır.  
  
3.  Her yol bileşenlerini X çiftinin /... (nokta nokta olan önceki yol bileşenleri tarafından oluşturulan üst dizini) kaldırılır.  
  
 İşlevi ardından pabs döndürür.  
  
## <a name="copy">Kopyalama</a>  
  
```  
void copy(const path& from, const path& to);
void copy(const path& from, const path& to, error_code& ec) noexcept;  
void copy(const path& from, const path& to, copy_options opts);
void copy(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;  
```  
  
 İşlevler büyük olasılıkla tüm kopyalayın veya konumunda bir veya daha fazla dosya bağlantısını `from` için `to` denetiminde `opts`, hiçbir aşırı copy_options::none olarak gerçekleştirilecek `opts` parametresi. `opts` en fazla birini içeren:  
  
-   skip_existing, overwrite_existing veya update_existing  
  
-   copy_symlinks veya skip_symlinks  
  
-   directories_only, create_symlinks veya create_hard_links  
  
 İşlevler ilk belirlemek için file_status değerleri f `from` ve için t `to`:  
  
-   if opts & (copy_options::create_symlinks &#124; copy_options::skip_symlinks), by calling symlink_status  
  
-   Aksi takdirde, durumu arayarak  
  
-   Aksi takdirde bir hata raporu.  
  
 Varsa! exists(f) &#124; &#124; eşdeğer (f, t) &#124; &#124; is_other(f) &#124; &#124; is_other(t) &#124; &#124; is_directory(f) & & is_regular_file(t), bunlar daha sonra bir hata raporu (ve başka hiçbir şey yapma).  
  
 Otherwise, if is_symlink(f) then:  
  
-   Seçenekler & copy_options::skip_symlinks hiçbir şey yapma varsa.  
  
-   Aksi halde, eğer! exists(t) & & Seçenekleri & copy_options::copy_symlinks sonra copy_symlink (Kimden için çevrilir).  
  
-   Aksi takdirde bir hata raporu.  
  
 Otherwise, if is_regular_file(f) then:  
  
-   Varsa çevrilir & copy_options::directories_only sonra yapın hiçbir şey.  
  
-   Aksi halde, eğer çevrilir & copy_options::create_symlinks sonra create_symlink(to, from).  
  
-   Aksi halde, eğer çevrilir & copy_options::create_hard_links sonra create_hard_link(to, from).  
  
-   Aksi halde, eğer is_directory(f) sonra copy_file (, çok/from.filename(), çevrilir).  
  
-   Aksi takdirde copy_file (Kimden için çevrilir).  
  
 Aksi halde, eğer is_directory(f) & & (çevrilir & copy_options::recursive &#124; &#124;! çevrilir) sonra:  
  
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
  
## <a name="opy_file"></a>  copy_file  
  
```  
bool copy_file(const path& from, const path& to);
bool copy_file(const path& from, const path& to, error_code& ec) noexcept;  
bool copy_file(const path& from, const path& to, copy_options opts);
bool copy_file(const path& from, const path& to, copy_options opts, error_code& ec) noexcept;  
```  
  
 İşlevler büyük olasılıkla tüm konumundaki dosya Kopyala `from` için `to` denetiminde `opts`, hiçbir aşırı copy_options::none olarak gerçekleştirilecek `opts` parametresi. `opts` en fazla bir skip_existing, overwrite_existing veya update_existing içeren.  
  
 Varsa mevcut\(için\) && \!\(çevrilir & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options::update_existing\) \) sonra rapor dosyası zaten var olan bir hata olarak.  
  
 Aksi halde, eğer \!var.\(için\) &#124; &#124; çevrilir & copy_options::overwrite_existing &#124; &#124; çevrilir & copy_options::update_existing & & last_write_time\(için \) \< last_write_time\(gelen\) &#124; &#124; \! \(çevrilir & \(copy_options::skip_existing &#124; copy_options::overwrite_existing &#124; copy_options:update_existing\) \) kopyalama girişiminde içeriği ve dosyasının dosyasına öznitelikleri. Kopyalama denemesi başarısız olursa hata olarak bildirin.  
  
 İşlevler doğru kopyalama girişiminde ve başarılı, aksi takdirde false döndürür.  
  
## <a name="copy_symlink "></a>  copy_symlink  
  
```  
void copy_symlink(const path& from, const path& to);
void copy_symlink(const path& from, const path& to, error_code& ec) noexcept;  
```  
  
 Varsa is_directory\(gelen\) işlevi çağırır create_directory_symlink\(gelen,\). Aksi takdirde create_symlink çağırır\(gelen,\).  
  
## <a name="create_directories"></a>  create_directories  
  
```  
bool create_directories(const path& pval);
bool create_directories(const path& pval, error_code& ec) noexcept;  
```  
  
 Gibi bir yol adı için bir\/b\/c işlevi dizinler oluşturur bir ve bir\/dizini oluşturabilmesi için gerektiğinde b bir\/b\/gerektiğinde c. Yalnızca dizin gerçekte oluşturduğu varsa true değerini döndürür `pval`.  
  
## <a name="create_directory"></a>  create_directory  
  
```  
bool create_directory(const path& pval);

bool create_directory(const path& pval, error_code& ec) noexcept;  
bool create_directory(const path& pval, const path& attr);
bool create_directory(const path& pval, const path& attr, error_code& ec) noexcept;  
```  
  
 İşlev dizini `pval` gerektiğinde. Yalnızca dizin gerçekte oluşturduğu varsa true değerini döndürür `pval`, bu durumda varolan dosyasından izinleri kopyalar `attr`, veya hiçbir aşırı perms::all kullanımları `attr` parametresi.  
  
## <a name="create_directory_symlink "></a>  create_directory_symlink  
  
```  
void create_directory_symlink(const path& to, const path& link);
void create_directory_symlink(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 Simgesel dizinine olarak bağlantı işlevi oluşturur `to`.  
  
## <a name="create_hard_link"></a>  create_hard_link  
  
```  
void create_hard_link(const path& to,  const path& link);
void create_hard_link(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 Dizin veya dosya sabit bağlantı olarak işlev bağlantısı oluşturur `to`.  
  
## <a name="create_symlink "></a>  create_symlink  
  
```  
void create_symlink(const path& to,  const path& link);

void create_symlink(const path& to, const path& link, error_code& ec) noexcept;  
```  
  
 İşlev oluşturur `link` simgesel dosyaya olarak `to`.  
  
## <a name="current_path"></a>  current_path  
  
```  
path current_path();
path current_path(error_code& ec);
void current_path(const path& pval);
void current_path(const path& pval, error_code& ec) noexcept;  
```  
  
 Hiçbir parametre işlevleriyle `pval` geçerli dizin için yol adını döndürür. Geçerli dizin kalan işlevleri kümesine `pval`.  
  
## <a name="end">Bitiş</a>  
  
```  
directory_iterator& end(const directory_iterator& iter) noexcept;  
recursive_directory_iterator& end(const recursive_directory_iterator& iter) noexcept;  
```  
  
 Directory_iterator ilk işlevi döndürür\( \) ve ikinci işlev recursive_directory_iterator döndürür\(\)  
  
## <a name="equivalent">eşdeğer</a>  
  
```  
bool equivalent(const path& left, const path& right);
bool equivalent(const path& left, const path& right, error_code& ec) noexcept;  
```  
  
 İşlevler ise true döndürür `left` ve `right` aynı dosya sistemi varlık belirleyin.  
  
## <a name="exists">var</a>  
  
```  
bool exists(file_status stat) noexcept;  
bool exists(const path& pval);
bool exists(const path& pval, error_code& ec) noexcept;  
```  
  
 Status_known ilk işlevi döndürür & & stat.type\( \) \! \= file_not_found. İkinci ve üçüncü işlevler döndürür bulunmaktadır\(durum\(pval\)\).  
  
## <a name="file_size"></a>  file_size  
  
```  
uintmax_t file_size(const path& pval);
uintmax_t file_size(const path& pval, error_code& ec) noexcept;  
```  
  
 Tarafından belirlenen dosyasının bayt cinsinden boyutu işlevler döndürür `pval`, mevcut\(pval\) & & is_regular_file\(pval\) ve dosya boyutu belirlenebilir. Aksi halde bunlar bir hata ve return uintmax_t rapor\(\-1\).  
  
## <a name="hard_link_count"></a>  hard_link_count  
  
```  
uintmax_t hard_link_count(const path& pval);
uintmax_t hard_link_count(const path& pval, error_code& ec) noexcept;  
```  
  
 İşlev için sabit bağlantıları sayısını döndürür `pval`, veya \-bir hata oluşursa, 1.  
  
## <a name="hash_value"></a>  hash_value  
  
```  
size_t hash_value(const path& pval) noexcept;  
```  
  
 İşlev pval.native için bir karma değer döndürür\(\).  
  
## <a name="is_block_file"></a>  is_block_file  
  
```  
bool is_block_file(file_status stat) noexcept;  
bool is_block_file(const path& pval);
bool is_block_file(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::block. Kalan işlevleri is_block_file dönmek\(durum\(pval\)\).  
  
## <a name="is_character_file"></a>  is_character_file  
  
```   
bool is_character_file(file_status stat) noexcept;  
bool is_character_file(const path& pval);
bool is_character_file(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::character. Kalan işlevleri is_character_file dönmek\(durum\(pval\)\).  
  
## <a name="is_directory "></a>  is_directory  
  
```   
bool is_directory(file_status stat) noexcept;  
bool is_directory(const path& pval);
bool is_directory(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::directory. Kalan işlevleri is_directory_file dönmek\(durum\(pval\)\).  
  
## <a name="is_empty"></a>  is_empty  
  
```   
bool is_empty(file_status stat) noexcept;  
bool is_empty(const path& pval);
bool is_empty(const path& pval, error_code& ec) noexcept;  
```  
  
 Varsa is_directory\(pval\) directory_iterator işlevi döndürür sonra\(pval\) \= \= directory_iterator\(\); Aksi takdirde file_ döndürür boyutu\(pval\) \= \= 0.  
  
## <a name="is_fifo"></a>  is_fifo  
  
```  
bool is_fifo(file_status stat) noexcept;  
bool is_fifo(const path& pval);
bool is_fifo(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::fifo. Kalan işlevleri is_fifo dönmek\(durum\(pval\)\).  
  
## <a name="is_other"></a>  is_other  
  
```  
bool is_other(file_status stat) noexcept;  
bool is_other(const path& pval);
bool is_other(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::other. Kalan işlevleri is_other dönmek\(durum\(pval\)\).  
  
## <a name="s_regular_file"></a>  is_regular_file  
  
```   
bool is_regular_file(file_status stat) noexcept;  
bool is_regular_file(const path& pval);
bool is_regular_file(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::regular. Kalan işlevleri is_regular_file dönmek\(durum\(pval\)\).  
  
## <a name="is_socket"></a>  is_socket  
  
```   
bool is_socket(file_status stat) noexcept;  
bool is_socket(const path& pval);
bool is_socket(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::socket. Kalan işlevleri is_socket dönmek\(durum\(pval\)\).  
  
## <a name="is_symlink"></a>  is_symlink  
  
```   
bool is_symlink(file_status stat) noexcept;  
bool is_symlink(const path& pval);
bool is_symlink(const path& pval, error_code& ec) noexcept;  
```  
  
 İlk işlev stat.type döndürür\( \) \= \= file_type::symlink. Kalan işlevleri is_symlink dönmek\(durum\(pval\)\).  
  
## <a name="last_write_time"></a>  last_write_time  
  
```   
file_time_type last_write_time(const path& pval);
file_time_type last_write_time(const path& pval, error_code& ec) noexcept;  
void last_write_time(const path& pval, file_time_type new_time);
void last_write_time(const path& pval, file_time_type new_time, error_code& ec) noexcept;  
```  
  
 İlk iki işlevler için son veri değişikliği zamanı döndürür `pval`, veya file_time_type\(\-1\) bir hata oluşursa. Son iki işlevleri için son veri değişikliği süresini ayarlamak `pval` new_time için.  
  
## <a name="permissions">İzinleri</a>  
  
```  
void permissions(const path& pval, perms mask);
void permissions(const path& pval, perms mask, error_code& ec) noexcept;  
```  
  
 İşlevler tarafından belirlenen pathname izinlerini ayarlama `pval` maskesi & izinleri denetiminde perms::mask & \(perms::add_perms &#124; perms::remove_perms\). Maske en çok bir perms::add_perms ve perms::remove_perms içeren.  
  
 Maske & perms::add_perms işlevleri durumuna izinleri varsa\(pval\).permissions\( \) &#124; maskesi & perms::mask. Aksi takdirde maskesi & perms::remove_perms işlevleri izinleri durumuna ayarlarsanız\(pval\).permissions\( \) & ~\(maskesi & perms::mask\). Aksi takdirde işlevleri maskesi & perms::mask izinlerini ayarlayın.  
  
## <a name="read_symlink"></a>  read_symlink  
  
```  
path read_symlink(const path& pval);
path read_symlink(const path& pval, error_code& ec);
```  
  
 Bir hata ve dönüş yolu işlevleri rapor\( \) varsa \!is_symlink\(pval\). Aksi takdirde işlevler türünde bir nesne döndürür `path` sembolik bağlantıyı içeren.  
  
## <a name="remove"></a>  Kaldır  
  
```  
bool remove(const path& pval);
bool remove(const path& pval, error_code& ec) noexcept;  
```  
  
 İşlevler yalnızca ise true var. döndürür\(symlink_status\(pval\) \) ve dosyayı başarıyla kaldırıldı. Bir simgesel kendisi kaldırıldı, onu atayan dosyası değil değildir.  
  
## <a name="remove_all"></a>  remove_all  
  
```  
uintmax_t remove_all(const path& pval);
uintmax_t remove_all(const path& pval, error_code& ec) noexcept;  
```  
  
 Varsa `pval` bir dizindir tüm dizin girişlerini sonra giriş işlevleri yinelemeli olarak kaldırın. Aksi takdirde işlevlerini Kaldır çağırın. Bunlar, başarılı bir şekilde kaldırılan tüm öğelerin sayısını döndürür.  
  
## <a name="rename">Yeniden Adlandır</a>  
  
```  
void rename(const path& from,  const path& to);
void rename(const path& from,  const path& to, error_code& ec) noexcept;  
```  
  
 İşlevleri yeniden adlandırın `from` için `to`. Bir simgesel kendisini yeniden adlandırılmış, atayan dosyası değil ' dir.  
  
## <a name="resize_file"></a>  resize_file  
  
```  
void resize(const path& pval, uintmax_t size);
void resize(const path& pval, uintmax_t size, error_code& ec) noexcept;  
```  
  
 Bu tür bir dosyanın boyutu işlevleri alter bu file_size\(pval\) \= \= boyutu  
  
## <a name="space">Alanı</a>  
  
```  
space_info space(const path& pval);
space_info space(const path& pval, error_code& ec) noexcept;  
```  
  
 İşlev tarafından belirlenen ses hakkında bilgi verir `pval`, yapı türü `space_info`. Yapı uintmax_t içerdiği\(\-1\) belirlenemiyor herhangi bir değer için.  
  
## <a name="status">Durumu</a>  
  
```  
file_status status(const path& pval);
file_status status(const path& pval, error_code& ec) noexcept;  
```  
  
 Pathname durum, dosya türü ve ilişkili izinler işlevleri dönmek `pval`. Bir simgesel kendisini test olmakla birlikte, bu dosyayı belirtir.  
  
## <a name="status_known"></a>  status_known  
  
```  
bool status_known(file_status stat) noexcept;  
```  
  
 Stat.type işlevi döndürür\( \) \! \= file_type::none  
  
## <a name="swap">Değiştirme</a>  
  
```  
void swap(path& left, path& right) noexcept;  
```  
  
 İşlev içeriğini alış verişleri `left` ve `right`.  
  
## <a name="symlink_status"></a>  symlink_status  
  
```  
file_status symlink_status(const path& pval);
file_status symlink_status(const path& pval, erroxr_code& ec) noexcept;  
```  
  
 Pathname simgesel durum, dosya türü ve ilişkili izinler işlevleri dönmek `pval`. İşlevler durumu olarak aynı şekilde davranır\(pval\) bir simgesel kendisini test olması dışında dosyanın değil, belirler.  
  
## <a name="system_complete"></a>  system_complete  
  
```  
path system_complete(const path& pval);
path system_complete(const path& pval, error_code& ec);
```  
  
 İşlevler, gerekirse hesabı kök adıyla ilişkilendirilmiş geçerli dizinin alır mutlak bir yol adı döndürür. \(POSIX için işlevleri mutlak dönmek\(pval\).\)  
  
## <a name="temp_directory_path"></a>  temp_directory_path  
  
```  
path temp_directory_path();
path temp_directory_path(error_code& ec);
```  
  
 İşlevler geçici dosyalar içeren için uygun bir dizin için bir yol döndürür.  
  
## <a name="u8path"></a>  u8path  
  
```  
template <class Source>  
path u8path(const Source& source);

template <class InIt>  
path u8path(InIt first, InIt last);
```  
  
 İlk işlev path(source) ile aynı şekilde davranır ve ikinci işlev yolu ile aynı şekilde davranır (ilk, son) dışında her durumda atanan kaynak dosya sistemi bağımsız olarak UTF-8 olarak kodlanmış char öğeleri dizisi olarak alınır.


