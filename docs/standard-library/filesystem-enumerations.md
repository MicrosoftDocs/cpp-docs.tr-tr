---
title: "&lt;dosya sistemi&gt; numaralandırmalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c6a6d7dcb0e0b0a8e655acbda0624f7fa5b70a8a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltfilesystemgt-enumerations"></a>&lt;dosya sistemi&gt; numaralandırmaları
Bu konuda dosya sistemi üstbilgi numaralandırmaları belgeler.

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<Deneysel/filesystem >    
 **Namespace:** std::experimental::filesystem  

##  <a name="copy_options"></a>  copy_options
İle birlikte kullanılan bit maskesi değerleri numaralandırması [kopya](http://msdn.microsoft.com/en-us/4af7a9b0-8861-45ed-b84e-0307f0669d60) ve [copy_file](http://msdn.microsoft.com/en-us/4af7a9b0-8861-45ed-b84e-0307f0669d60) işlevleri davranışı belirtin.  
  
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
|`none`|Varsayılan davranış için işlem gerçekleştirilemiyor.|  
|`skip_existing`|Dosya zaten mevcutsa kopyalamayın bir hata raporu gönderme.|  
|`overwrite_existing`|Zaten varsa bu dosyanın üzerine.|  
|`update_existing`|Zaten varsa ve değiştirme eski bir dosyanın üzerine yazın.|  
|`recursive`|Yinelemeli olarak dizinler ve içeriklerini kopyalayın.|  
|`copy_symlinks`|Bunların işaret dosyaları kopyalamak yerine sembolik bağlantılar olarak sembolik bağlantılar kopyalayın.|  
|`skip_symlinks`|Sembolik bağlantılar yoksay.|  
|`directories_only`|Yalnızca dizinlerini yineleme, dosyaları yoksayar.|  
|`create_symlinks`|Dosyaları kopyalamak yerine sembolik bağlantılar olun. Hedef geçerli dizin olduğu sürece bir mutlak yol kaynak yolu olarak kullanılmalıdır.|  
|`create_hard_links`|Dosyaları kopyalamak yerine sabit bağlantıları olun.|  
  

##  <a name="directory_options"></a> directory_options
Dizinleri sembolik bağlantılar izleyin mi, yoksa bunları yoksaymak için belirtir.  
  
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
|`none`|Varsayılan davranış: dizinlere sembolik bağlantılar yoksay. İzin reddedildi bir hatadır.|  
|`follow_directory_symlink`|Sembolik bağlantılar dizinleri gerçek dizinleri olarak kabul eder.|  
  
##  <a name="file_type"></a>  file_type
Dosya türleri için numaralandırması. Normal, dizin, not_found ve bilinmeyen değerleri desteklenir.  
  
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
|`not_found`|-1|Var olmayan bir dosyayı temsil eder.|  
|`none`|0|Type özniteliği olan bir dosyayı temsil eder. (Desteklenmez.)|  
|`regular`|1.|Geleneksel disk dosyası temsil eder.|  
|`directory`|2|Bir dizin temsil eder.|  
|`symlink`|3|Sembolik bağlantıyı temsil eder. (Desteklenmez.)|  
|`block`|4|Bir blok özel dosyası UNIX tabanlı sistemlerde temsil eder. (Desteklenmez.)|  
|`character`|5|Bir özel karakter dosyası UNIX tabanlı sistemlerde temsil eder. (Desteklenmez.)|  
|`fifo`|6|UNIX tabanlı sistemlerde FIFO dosyayı temsil eder. (Desteklenmez.)|  
|`socket`|7|UNIX tabanlı sistemlerde yuvasını temsil eder. (Desteklenmez.)|  
|`unknown`|8|Durumu belirlenemiyor bir dosyayı temsil eder.|  
  
##  <a name="perms"></a>  izinleri
Dosya izinleri bayrakları. Aslında "readonly" değerleri desteklenir ve tüm. Bir salt okunur dosya için hiçbiri * _write BITS ayarlanır. Aksi takdirde `all` bit (0x0777) ayarlanır.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<filesystem>](../standard-library/filesystem.md)

