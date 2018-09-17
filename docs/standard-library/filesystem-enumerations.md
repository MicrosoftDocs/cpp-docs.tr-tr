---
title: '&lt;dosya sistemi&gt; sabit listeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::filesystem::copy_options
- filesystem/std::experimental::filesystem::copy_options
- filesystem/std::filesystem::directory_options
- filesystem/std::experimental::filesystem::directory_options
- filesystem/std::filesystem::file_type
- filesystem/std::experimental::filesystem::file_type
- filesystem/std::filesystem::perms
- filesystem/std::experimental::filesystem::perms
dev_langs:
- C++
ms.assetid: 0096c046-d101-464c-8259-b878a48280b0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ff655573f77b901725fe18c2346c46306c9b853a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716813"
---
# <a name="ltfilesystemgt-enumerations"></a>&lt;dosya sistemi&gt; sabit listeleri

Bu konuda, dosya sistemi üst bilgisindeki numaralandırmalar belgeler.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<Deneysel/filesystem >

**Namespace:** std::experimental::filesystem

## <a name="copy_options"></a>  copy_options

İle kullanılan bit maskesi değerlerinin numaralandırması [kopyalama](filesystem-functions.md#copy) ve [copy_file](filesystem-functions.md#copy_file) davranışını belirtmek için işlev.

### <a name="syntax"></a>Sözdizimi

```cpp
enum class copy_options {
   none = 0,
   skip_existing = 1,
   overwrite_existing = 2,
   update_existing = 4,
   recursive = 8,
   copy_symlinks = 16,
   skip_symlinks = 32,
   directories_only = 64,
   create_symlinks = 128,
   create_hard_links = 256
};
```

### <a name="values"></a>Değerler

|`Name`|Açıklama|
|------------|-----------------|
|`none`|Varsayılan davranışı için işlemi gerçekleştirin.|
|`skip_existing`|Dosya zaten varsa, kopyalamayın bir hata bildirmez.|
|`overwrite_existing`|Zaten varsa dosyasının üzerine yazın.|
|`update_existing`|Zaten var ve değişiklik eski dosyasının üzerine yazın.|
|`recursive`|Yinelemeli olarak alt dizinleri ve içeriklerini kopyalayın.|
|`copy_symlinks`|Sembolik bağlantılar, bunlar üzerine gelin dosyaları kopyalamak yerine sembolik bağlantıları olarak kopyalayın.|
|`skip_symlinks`|Sembolik bağlantıları yoksayar.|
|`directories_only`|Yalnızca dizinleri yineleme yapma, dosyaları yoksayar.|
|`create_symlinks`|Dosyaları kopyalamak yerine simgesel bağlantılar olun. Geçerli dizin hedef olmadığı sürece kaynak yolu mutlak bir yol kullanılması gerekir.|
|`create_hard_links`|Dosyaları kopyalamak yerine sabit bağlantılar olun.|


## <a name="directory_options"></a> directory_options

Sembolik bağlantılar dizinleri takip etmek veya bunların yoksayılması için belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
enum class directory_options {
   none = 0,
   follow_directory_symlink
};
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`none`|Varsayılan davranış: dizinleri sembolik bağlantıları yoksayar. İzin reddedildi; bir hatadır.|
|`follow_directory_symlink`|Sembolik bağlantılar dizinleri gerçek dizin kabul eder.|

## <a name="file_type"></a>  file_type

Dosya türleri için bir sabit listesi. Desteklenen normal, dizin, not_found ve bilinmeyen değerlerdir.

### <a name="syntax"></a>Sözdizimi

```cpp
enum class file_type {
    not_found = -1,
    none,
    regular,
    directory,
    symlink,
    block,
    character,
    fifo,
    socket,
    unknown
};
```

### <a name="values"></a>Değerler

|Ad|Değer|Açıklama|
|----------|-----------|-----------------|
|`not_found`|-1|Mevcut bir dosyayı temsil eder.|
|`none`|0|Hiçbir tür özniteliği olan bir dosyayı temsil eder. (Desteklenmiyor.)|
|`regular`|1.|Geleneksel disk dosyasını temsil eder.|
|`directory`|2|Bir dizin temsil eder.|
|`symlink`|3|Sembolik bağlantıyı temsil eder. (Desteklenmiyor.)|
|`block`|4|UNIX tabanlı sistemlerde bir blok özel dosyasını temsil eder. (Desteklenmiyor.)|
|`character`|5|UNIX tabanlı sistemlerde bir özel karakter dosyasını temsil eder. (Desteklenmiyor.)|
|`fifo`|6|Bir FIFO dosyasını UNIX tabanlı sistemlerde temsil eder. (Desteklenmiyor.)|
|`socket`|7|Bir yuva UNIX tabanlı sistemlerde temsil eder. (Desteklenmiyor.)|
|`unknown`|8|Durumu belirlenemediğinden bir dosyayı temsil eder.|

## <a name="perms"></a>  izinleri

Dosya izinleri bayrakları. Desteklenen değerler şunlardır: temelde "salt okunur" ve tümü. Bir salt okunur dosya için hiçbir * _write bit ayarlanır. Aksi takdirde `all` (0x0777) bitinin ayarlanmasıdır.

### <a name="syntax"></a>Sözdizimi

```cpp
enum class perms {// names for permissions
   none = 0,
   owner_read = 0400,  // S_IRUSR
   owner_write = 0200, // S_IWUSR
   owner_exec = 0100,  // S_IXUSR
   owner_all = 0700,   // S_IRWXU
   group_read = 040,   // S_IRGRP
   group_write = 020,  // S_IWGRP
   group_exec = 010,   // S_IXGRP
   group_all = 070,    // S_IRWXG
   others_read = 04,   // S_IROTH
   others_write = 02,  // S_IWOTH
   others_exec = 01,   // S_IXOTH
   others_all = 07,    // S_IRWXO
   all = 0777,
   set_uid = 04000,    // S_ISUID
   set_gid = 02000,    // S_ISGID
   sticky_bit = 01000, // S_ISVTX
   mask = 07777,
   unknown = 0xFFFF,
   add_perms = 0x10000,
   remove_perms = 0x20000,
   resolve_symlinks = 0x40000
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<FileSystem >](../standard-library/filesystem.md)<br/>
