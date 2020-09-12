---
title: '&lt;dosya sistemi &gt; numaralandırmaları'
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
ms.openlocfilehash: 3c94ec899f0ea7abf71530f6aca44638fdb216c9
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041945"
---
# <a name="ltfilesystemgt-enumerations"></a>&lt;dosya sistemi &gt; numaralandırmaları

Bu konu, dosya sistemi üstbilgisindeki numaralandırmaları belgeler.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<experimental/filesystem>

**Ad alanı:** std:: deneysel:: FileSystem

## <a name="copy_options"></a><a name="copy_options"></a> copy_options

Davranışı belirtmek için [Copy](filesystem-functions.md#copy) ve [copy_file](filesystem-functions.md#copy_file) işlevleriyle kullanılan bit maskesi değerlerinin numaralandırması.

### <a name="syntax"></a>Syntax

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

| Ad | Açıklama |
|------------|-----------------|
|`none`|İşlem için varsayılan davranışı gerçekleştirin.|
|`skip_existing`|Dosya zaten varsa kopyalamayın bir hata raporlamayın.|
|`overwrite_existing`|Zaten varsa dosyanın üzerine yazın.|
|`update_existing`|Zaten varsa dosyanın üzerine yazın ve değiştirme özelliğinden daha eski olur.|
|`recursive`|Alt dizinleri ve bunların içeriğini özyinelemeli olarak kopyalayın.|
|`copy_symlinks`|Sembolik bağlantıları, işaret ettikleri dosyaları kopyalamak yerine sembolik bağlantılar olarak kopyalayın.|
|`skip_symlinks`|Sembolik bağlantıları yoksayın.|
|`directories_only`|Yalnızca dizinler üzerinde yineleme yapın, dosyaları yoksayın.|
|`create_symlinks`|Dosyaları kopyalamak yerine sembolik bağlantılar yapın. Hedef geçerli dizin olmadığı sürece kaynak yolu olarak mutlak bir yol kullanılmalıdır.|
|`create_hard_links`|Dosyaları kopyalamak yerine sabit bağlantılar oluşturun.|

## <a name="directory_options"></a><a name="directory_options"></a> directory_options

Dizinlerin sembolik bağlantılarının takip edilip edilmeyeceğini belirtir veya bunları yok sayın.

### <a name="syntax"></a>Syntax

```cpp
enum class directory_options {
   none = 0,
   follow_directory_symlink
};
```

### <a name="values"></a>Değerler

|Ad|Açıklama|
|----------|-----------------|
|`none`|Varsayılan davranış: dizinlere sembolik bağlantıları yoksayın. İzin reddedildi hatası.|
|`follow_directory_symlink`|Gerçek dizinler olarak dizinlere sembolik bağlantıları değerlendirin.|

## <a name="file_type"></a><a name="file_type"></a> file_type

Dosya türleri için bir sabit listesi. Desteklenen değerler normal, dizin, not_found ve bilinmelidir.

### <a name="syntax"></a>Syntax

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

|Name|Değer|Açıklama|
|----------|-----------|-----------------|
|`not_found`|-1|Varolmayan bir dosyayı temsil eder.|
|`none`|0|Tür özniteliği olmayan bir dosyayı temsil eder. (Desteklenmiyor.)|
|`regular`|1|Geleneksel bir disk dosyasını temsil eder.|
|`directory`|2|Bir dizini temsil eder.|
|`symlink`|3|Sembolik bir bağlantıyı temsil eder. (Desteklenmiyor.)|
|`block`|4|UNIX tabanlı sistemlerde blok özel bir dosyayı temsil eder. (Desteklenmiyor.)|
|`character`|5|UNIX tabanlı sistemlerde karakter özel bir dosyayı temsil eder. (Desteklenmiyor.)|
|`fifo`|6|UNIX tabanlı sistemlerde bir FıFO dosyasını temsil eder. (Desteklenmiyor.)|
|`socket`|7|UNIX tabanlı sistemlerde bir yuvayı temsil eder. (Desteklenmiyor.)|
|`unknown`|8|Durumu belirlenemediği bir dosyayı temsil eder.|

## <a name="perm_options"></a><a name="perm_options"></a> perm_options

,, `replace` Ve değerlerini içerir `add` `remove` `nofollow` .

```cpp
enum class perm_options;
```

## <a name="perms"></a><a name="perms"></a> izinleri

Dosya izinleri için bayraklar. Desteklenen değerler temelde "ReadOnly" ve hepsi. Salt okunur bir dosya için, * _write bitlerin hiçbiri ayarlanmadı. Aksi halde `all` bit (0x0777) ayarlanır.

### <a name="syntax"></a>Syntax

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

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)
