---
title: "Dosya arama işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
apitype: DLLExport
dev_langs:
- C++
helpviewer_keywords:
- file names [C++], searching for
- _find function
- wfind function
- find function
- _wfind function
ms.assetid: 2bc2f8ef-44e4-4271-b3e8-666d36fde828
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 16aff4db1a04c31b3b45c9a61f74c44d6c9465f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="filename-search-functions"></a>Dosya arama işlevleri
Bu işlevler için arama yapın ve belirtilen dosya adları için aramaları kapatın:  
  
-   [_findnext, _wfindnext](../c-runtime-library/reference/findnext-functions.md)  
  
-   [_findfirst, _wfindfirst](../c-runtime-library/reference/findfirst-functions.md)  
  
-   [_findclose](../c-runtime-library/reference/findclose.md)  
  
## <a name="remarks"></a>Açıklamalar  
 `_findfirst` İşlevi belirtilen dosya ile eşleşen bir dosya adı ilk örneği hakkında bilgi sağlar `filespec` bağımsız değişkeni. Kullanabileceğiniz `filespec` ana bilgisayar işletim sistemi tarafından desteklenen herhangi bir birleşimini joker karakter.  
  
 Dosya bilgileri işlevler döndürür bir `_finddata_t` IO.h içinde tanımlanan yapısı. Pek çok Çeşitleme ailesindeki çeşitli işlevleri kullanılacağı `_finddata_t` yapısı. Temel `_finddata_t` yapısı aşağıdaki öğeleri içerir:  
  
 `unsigned attrib`  
 Dosya özniteliği.  
  
 `time_t time_create`  
 Dosya oluşturma (FAT dosya sistemleri için-1 M) süresi. Bu süre UTC biçiminde depolanır. Yerel saat olarak dönüştürmek için [localtime_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).  
  
 `time_t time_access`  
 Son dosya erişimi (FAT dosya sistemleri için-1 M) süresi. Bu süre UTC biçiminde depolanır. Yerel saat olarak dönüştürmek için `localtime_s`.  
  
 `time_t time_write`  
 Dosyaya son yazma zamanı. Bu süre UTC biçiminde depolanır. Yerel saat olarak dönüştürmek için `localtime_s`.  
  
 `_fsize_t size`  
 Dosyanın bayt cinsinden uzunluğu.  
  
 `char name`[ `_MAX_PATH`]  
 Sonlandırılmış adı eşleşen dosya veya dizin yolunu olmadan.  
  
 Oluşturma ve FAT sistemi gibi bir dosyaya son erişim sayılarının desteklemez dosya sistemlerinde `time_create` ve `time_access` alanları her zaman-1 M.  
  
 `_MAX_PATH`içinde Stdlib.h 260 bayt olarak tanımlanır.  
  
 Hedef öznitelikleri belirtilemez (gibi `_A_RDONLY`) bulma işlemi sınırlamak için. Bu öznitelikler döndürülür `attrib` alanını `_finddata_t` yapısı ve (tanımlıysa IO.h) aşağıdaki değerlere sahip olabilir. Kullanıcıların değil Bel bu değerleri yalnızca mümkün olan `attrib` alan.  
  
 `_A_ARCH`  
 Arşiv. Dosya değiştirildi ve tarafından temizlenmiş her **yedekleme** komutu. Değer: 0x20.  
  
 `_A_HIDDEN`  
 Gizli bir dosya. Kullanmadığınız sürece DIR komutuyla değil genellikle görülen **/AH** seçeneği. Normal dosyaları ve bu özniteliği olan dosyaları hakkında bilgi verir. Değer: 0x02.  
  
 `_A_NORMAL`  
 Normal. Dosya yok sahip diğer öznitelikleri ayarlamak ve okunabilir veya yazılabilir kısıtlama. Değer: 0x00.  
  
 `_A_RDONLY`  
 Salt okunur. Dosya yazma için açılamıyor ve aynı ada sahip bir dosya oluşturulamaz. Değer: 0x01.  
  
 `_A_SUBDIR`  
 Alt dizin. Değer: 0x10.  
  
 `_A_SYSTEM`  
 Sistem dosyası. İle değil normalde görülen **DIR** sürece komut **/A** veya **/A:S** seçenek kullanılır. Değer: 0x04.  
  
 `_findnext`sonraki adı varsa, eşleşen bulur `filespec` önceki bir çağrıda belirtilen bağımsız değişken `_findfirst`. `fileinfo` Bağımsız değişkeni için önceki çağrı tarafından başlatılan bir yapı noktasına `_findfirst`. Bir eşleşme bulunamazsa `fileinfo` yapısı içeriği daha önce açıklandığı şekilde değiştirilir. Aksi halde sol değişmez. `_findclose`Belirtilen arama tanıtıcısı kapatır ve ilişkili tüm kaynakları için her ikisini de serbest `_findfirst` ve `_findnext`. Tarafından döndürülen tanıtıcı `_findfirst` veya `_findnext` için ilk geçirilmelidir `_findclose`, geçirilen yolları form dizinleri silme gibi değiştirme işlemleri gerçekleştirilmeden önce.  
  
 Geçirebilmenize `_find` işlevleri. Örneğin, bir çağrı varsa `_findfirst` veya `_findnext` alt, yeni bir arama dosyasını, başka bir çağrıyı ile başlatılabilir bulur `_findfirst` veya `_findnext`.  
  
 `_wfindfirst`ve `_wfindnext` joker karakter sürümleri `_findfirst` ve `_findnext`. Joker karakter sürümlerinin yapısı bağımsız `_wfinddata_t` IO.h ve Wchar.h tanımlı veri türü. Bu veri türü alanlarının aynıdır `_finddata_t` dışında veri türü `_wfinddata_t` ad alanı türüdür `wchar_t` türü yerine `char`. Aksi takdirde `_wfindfirst` ve `_wfindnext` aynı şekilde davranır `_findfirst` ve `_findnext`.  
  
 `_findfirst`ve `_findnext` 64-bit süre türünü kullanın. Eski 32-bit zamanı tür kullanmanız gerekiyorsa, tanımlayabilirsiniz `_USE_32BIT_TIME_T`. Bu işlevleri sürümleri `32` adlarında soneki kullanan 32-bit zaman türü ve olanlar `64` soneki 64-bit zaman tür kullanın.  
  
 İşlevler `_findfirst32i64`, `_findnext32i64`, `_wfindfirst32i64`, ve `_wfindnext32i64` de kullanın ve 64-bit dosya uzunlukları dönüş dışında aynı şekilde bu işlevlerin 32-bit zaman türü sürümleri davranır. İşlevler `_findfirst64i32`, `_findnext64i32`, `_wfindfirst64i32`, ve `_wfindnext64i32` 64-bit zamanı tür kullanır ancak 32-bit dosya uzunlukları kullanır. Bu işlevler uygun varyasyonları kullanmak `_finddata_t` hangi alanların farklı türlerine sahip zaman ve dosya boyutu için türü.  
  
 `_finddata_t`gerçekte değerlendiren bir makro `_finddata64i32_t` (veya `_finddata32_t` varsa `_USE_32BIT_TIME_T` tanımlanır). Üzerinde çeşitlemeleri aşağıdaki tabloda özetlenmiştir `_finddata_t`:  
  
|Yapı|Zaman türü|Dosya boyutu türü|  
|---------------|---------------|--------------------|  
|`_finddata_t`, `_wfinddata_t`|`__time64_t`|`_fsize_t`|  
|`_finddata32_t`, `_wfinddata32_t`|`__time32_t`|`_fsize_t`|  
|`__finddata64_t`, `__wfinddata64_t`|`__time64_t`|`__int64`|  
|`_finddata32i64_t`, `_wfinddata32i64_t`|`__time32_t`|`__int64`|  
|`_finddata64i32_t`, `_wfinddata64i32_t`|`__time64_t`|`_fsize_t`|  
  
 `_fsize_t`olan bir `typedef` için `unsigned long` (32 bit).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_find.c  
// This program uses the 32-bit _find functions to print  
// a list of all files (and their attributes) with a .C extension  
// in the current directory.  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <io.h>  
#include <time.h>  
  
int main( void )  
{  
   struct _finddata_t c_file;  
   intptr_t hFile;  
  
   // Find first .c file in current directory   
   if( (hFile = _findfirst( "*.c", &c_file )) == -1L )  
      printf( "No *.c files in current directory!\n" );  
   else  
   {  
      printf( "Listing of .c files\n\n" );  
      printf( "RDO HID SYS ARC  FILE         DATE %25c SIZE\n", ' ' );  
      printf( "--- --- --- ---  ----         ---- %25c ----\n", ' ' );  
      do {  
         char buffer[30];  
         printf( ( c_file.attrib & _A_RDONLY ) ? " Y  " : " N  " );  
         printf( ( c_file.attrib & _A_HIDDEN ) ? " Y  " : " N  " );  
         printf( ( c_file.attrib & _A_SYSTEM ) ? " Y  " : " N  " );  
         printf( ( c_file.attrib & _A_ARCH )   ? " Y  " : " N  " );  
         ctime_s( buffer, _countof(buffer), &c_file.time_write );  
         printf( " %-12s %.24s  %9ld\n",  
            c_file.name, buffer, c_file.size );  
      } while( _findnext( hFile, &c_file ) == 0 );  
      _findclose( hFile );  
   }  
}  
```  
  
```Output  
Listing of .c files  
  
RDO HID SYS ARC  FILE         DATE                           SIZE  
--- --- --- ---  ----         ----                           ----  
 N   N   N   Y   blah.c       Wed Feb 13 09:21:42 2002       1715  
 N   N   N   Y   test.c       Wed Feb 06 14:30:44 2002        312  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sistem Çağrıları](../c-runtime-library/system-calls.md)