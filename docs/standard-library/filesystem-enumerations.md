---
title: '&lt;dosya&gt; sistemi hesaplamaları'
ms.date: 11/04/2016
f1_keywords:
- filesystem/std::filesystem::copy_options
- filesystem/std::experimental::filesystem::copy_options
- filesystem/std::filesystem::directory_options
- filesystem/std::experimental::filesystem::directory_options
- filesystem/std::filesystem::file_type
- filesystem/std::experimental::filesystem::file_type
- filesystem/std::filesystem::perms
- filesystem/std::experimental::filesystem::perms
ms.assetid: 0096c046-d101-464c-8259-b878a48280b0
ms.openlocfilehash: 0d5b31b31f9f435c52db89521b4b753c16d86501
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368423"
---
# <a name="ltfilesystemgt-enumerations"></a>&lt;dosya&gt; sistemi hesaplamaları

Bu konu, dosya sistemi üstbilgisinde yer alan enumları belgeler.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<deneysel/filesystem>

**Ad alanı:** std::deneysel::filesystem

## <a name="copy_options"></a><a name="copy_options"></a>copy_options

Davranışı belirtmek için [kopyalama](filesystem-functions.md#copy) ve [copy_file](filesystem-functions.md#copy_file) işlevleri ile kullanılan bitmask değerlerinin numaralandırması.

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
|`none`|İşlem için varsayılan davranışı gerçekleştirin.|
|`skip_existing`|Dosya zaten varsa kopyalamayın, bir hata bildirin.|
|`overwrite_existing`|Zaten varsa dosyanın üzerine yazın.|
|`update_existing`|Dosyanın zaten varsa ve değiştirmeden daha eskiyse üzerine yazın.|
|`recursive`|Alt dizinleri ve içeriğini yinede kopyalayın.|
|`copy_symlinks`|Işaret ettikleri dosyaları kopyalamak yerine sembolik bağlantıları sembolik bağlantılar olarak kopyalayın.|
|`skip_symlinks`|Sembolik bağlantıları yoksay.|
|`directories_only`|Yalnızca dizinler üzerinde yineleyin, dosyaları yoksayın.|
|`create_symlinks`|Dosyaları kopyalamak yerine sembolik bağlantılar yapın. Hedef geçerli dizin olmadığı sürece mutlak bir yol kaynak yol olarak kullanılmalıdır.|
|`create_hard_links`|Dosyaları kopyalamak yerine sabit bağlantılar yapın.|

## <a name="directory_options"></a><a name="directory_options"></a>directory_options

Dizinlere sembolik bağlantıları izleyip izlememe mi yoksa bunları yok saymak mı gerektiğini belirtir.

### <a name="syntax"></a>Sözdizimi

```cpp
enum class directory_options {
   none = 0,
   follow_directory_symlink
};
```

### <a name="values"></a>Değerler

|Adı|Açıklama|
|----------|-----------------|
|`none`|Varsayılan davranış: dizinlere sembolik bağlantıları yoksay. Reddedilen izin bir hatadır.|
|`follow_directory_symlink`|Dizinlere olan sembolik bağlantıları gerçek dizinler olarak ele a.nın.|

## <a name="file_type"></a><a name="file_type"></a>file_type

Dosya türleri için numaralandırma. Desteklenen değerler düzenli, dizin, not_found ve bilinmiyor.

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

|Adı|Değer|Açıklama|
|----------|-----------|-----------------|
|`not_found`|-1|Var olmayan bir dosyayı temsil eder.|
|`none`|0|Tür özniteliği olmayan bir dosyayı temsil eder. (Desteklenmez.)|
|`regular`|1|Geleneksel bir disk dosyanı temsil eder.|
|`directory`|2|Bir dizini temsil eder.|
|`symlink`|3|Sembolik bir bağlantıyı temsil eder. (Desteklenmez.)|
|`block`|4|UNIX tabanlı sistemlerde bloka özel bir dosyayı temsil eder. (Desteklenmez.)|
|`character`|5|UNIX tabanlı sistemlerde karaktere özel bir dosyayı temsil eder. (Desteklenmez.)|
|`fifo`|6|UNIX tabanlı sistemlerde bir FIFO dosyayı temsil eder. (Desteklenmez.)|
|`socket`|7|UNIX tabanlı sistemlerde bir sokettemsil eder. (Desteklenmez.)|
|`unknown`|8|Durumu belirlenemeyen bir dosyayı temsil eder.|

## <a name="perm_options"></a><a name="perm_options"></a>perm_options

Değerleri `replace`, `add` `remove`, `nofollow`, ve .

```cpp
enum class perm_options;
```

## <a name="perms"></a><a name="perms"></a>Perma

Dosya izinleri için bayraklar. Desteklenen değerler aslında "yalnızca okunur" ve tüm. Yalnızca okunan bir dosya için *_write bitlerinin hiçbiri ayarlanır. Aksi `all` takdirde bit (0x0777) ayarlanır.

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

[Üstbilgi Dosyaları Başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<dosya sistemi>](../standard-library/filesystem.md)
