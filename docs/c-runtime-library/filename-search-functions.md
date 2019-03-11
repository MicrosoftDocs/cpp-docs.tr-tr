---
title: Filename işlevleri Ara
ms.date: 11/04/2016
apilocation:
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
apitype: DLLExport
helpviewer_keywords:
- file names [C++], searching for
- _find function
- wfind function
- find function
- _wfind function
ms.assetid: 2bc2f8ef-44e4-4271-b3e8-666d36fde828
ms.openlocfilehash: aebdf2e5aaf6d59e5ee39af05540604206ec6c23
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57740543"
---
# <a name="filename-search-functions"></a>Filename işlevleri Ara

Bu işlevler için arama yapın ve belirtilen dosya adlarını arar kapatın:

- [_findnext, _wfindnext](../c-runtime-library/reference/findnext-functions.md)

- [_findfirst, _wfindfirst](../c-runtime-library/reference/findfirst-functions.md)

- [_findclose](../c-runtime-library/reference/findclose.md)

## <a name="remarks"></a>Açıklamalar

`_findfirst` İşlevi ilk örneğinin belirtilen dosya ile eşleşen bir dosya adı hakkında bilgi sağlar `filespec` bağımsız değişken. Kullanabileceğiniz `filespec` konak işletim sistemi tarafından desteklenen herhangi bir birleşimini joker karakter.

Dosya bilgilerinin işlevler döndürür bir `_finddata_t` IO.h içinde tanımlanan yapısı. Çeşitli türleri çeşitli işlevler ailedeki kullanın `_finddata_t` yapısı. Temel `_finddata_t` yapısı aşağıdaki öğeleri içerir:

`unsigned attrib`<br/>
Dosya özniteliği.

`time_t time_create`<br/>
Dosya oluşturma (FAT dosya sistemleri için-1 L) zamanı. Bu süre UTC biçiminde depolanır. Yerel saat olarak dönüştürmek için [localtime_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md).

`time_t time_access`<br/>
Son dosya erişimi (FAT dosya sistemleri için-1 L) zamanı. Bu süre UTC biçiminde depolanır. Yerel saat olarak dönüştürmek için `localtime_s`.

`time_t time_write`<br/>
Dosyasının son yazma zamanı. Bu süre UTC biçiminde depolanır. Yerel saat olarak dönüştürmek için `localtime_s`.

`_fsize_t size`<br/>
Dosyanın bayt cinsinden uzunluğu.

`char name`[ `_MAX_PATH`] Eşleşen dosya veya yol olmadan, dizin adı null ile sonlandırılmış.

FAT sistemi gibi bir dosyanın son erişim zamanları ve oluşturma desteklemeyen dosya sistemlerinde `time_create` ve `time_access` alanları her zaman-1 L.

`_MAX_PATH` 260 bayt olarak Stdlıb.h içinde tanımlanır.

Hedef öznitelikleri belirtilemez (gibi `_A_RDONLY`) bulma işlemi sınırlamak için. Bu öznitelikler döndürülür `attrib` alanını `_finddata_t` yapısı ve (tanımlıysa IO.h) aşağıdaki değerlere sahip olabilir. Kullanıcılar değil Bu değerler yalnızca mümkün olan güvenin `attrib` alan.

`_A_ARCH`<br/>
Arşiv. Dosya değiştirildi ve tarafından temizlenmiş her **yedekleme** komutu. Değer: 0x20.

`_A_HIDDEN`<br/>
Gizli bir dosya. DIR komutunun ile kullanmadığınız sürece değil genel olarak görülen **/AH** seçeneği. Normal dosyalar ve bu özniteliğe sahip dosyalar hakkında bilgi döndürür. Değer: 0x02.

`_A_NORMAL`<br/>
Normal. Dosya yok diğer öznitelikler ayarlayın ve okunabilir veya kısıtlama yazılır. Değer: 0x00.

`_A_RDONLY`<br/>
Salt okunur. Dosya yazma için açılamıyor ve aynı ada sahip bir dosya oluşturulamıyor. Değer: 0x01.

`_A_SUBDIR`<br/>
Alt. Değer: 0x10.

`_A_SYSTEM`<br/>
Sistem dosyası. Normalde olmayan görüldüğü **DIR** sürece komutu **/A** veya **/A:S** seçeneği kullanılır. Değer: 0x04.

`_findnext` sonraki adı varsa, eşleşen bulur `filespec` çağrısında belirtilen bağımsız değişken `_findfirst`. `fileinfo` Bağımsız değişkeni için yapılan önceki çağrı tarafından başlatılan bir yapıya işaret etmelidir `_findfirst`. Bir eşleşme bulunursa `fileinfo` yapısı içeriği daha önce açıklanan şekilde değiştirilir. Aksi halde sol değişmez. `_findclose` Belirtilen arama tanıtıcı kapatır ve hem ilişkili tüm kaynakları serbest `_findfirst` ve `_findnext`. Tarafından döndürülen tanıtıcı `_findfirst` veya `_findnext` ilk geçirilmelidir `_findclose`, silme gibi değiştirme işlemleri, geçirilen yolları oluşturan dizinleri gerçekleştirilmeden önce.

İç içe yerleştirebilirsiniz `_find` işlevleri. Örneğin, bir çağrı `_findfirst` veya `_findnext` bulur, yeni bir arama bir alt dosyanın başka bir çağrı ile başlatılabilir `_findfirst` veya `_findnext`.

`_wfindfirst` ve `_wfindnext` geniş karakterli sürümleridir `_findfirst` ve `_findnext`. Geniş karakter sürümleri yapısı bağımsız `_wfinddata_t` IO.h ve wchar.h içinde tanımlanan veri türü. Bu veri türü alanlarını aynıdır `_finddata_t` dışında veri türü `_wfinddata_t` ad alanı türünde `wchar_t` tür yerine `char`. Aksi takdirde `_wfindfirst` ve `_wfindnext` öğesine aynı şekilde davranır `_findfirst` ve `_findnext`.

`_findfirst` ve `_findnext` 64-bit zaman türünü kullanın. Eski 32-bit zaman türü kullanmanız gerekirse, tanımlayabileceğiniz `_USE_32BIT_TIME_T`. Sahip bu işlevlerin sürümleri `32` adlarında soneki kullanıp 32-bit zaman türü ve olanlar `64` soneki 64-bit zaman türü kullanın.

İşlevleri `_findfirst32i64`, `_findnext32i64`, `_wfindfirst32i64`, ve `_wfindnext32i64` ayrıca kullanın ve 64 bit dosya uzunlukları dönüş dışında aynı şekilde bu işlevlerin 32-bit zaman türü sürümleri davranır. İşlevleri `_findfirst64i32`, `_findnext64i32`, `_wfindfirst64i32`, ve `_wfindnext64i32` 64-bit zaman türü kullanır ancak 32 bitlik dosya uzunluklarını kullanacak. Bu işlevleri uygun çeşitlerini kullanın `_finddata_t` hangi alanların sahip farklı zaman ve dosya boyutu için türü.

`_finddata_t` Aslında değerlendiren makro `_finddata64i32_t` (veya `_finddata32_t` varsa `_USE_32BIT_TIME_T` tanımlanır). Aşağıdaki tabloda çeşitlemeleri özetler `_finddata_t`:

|Yapı|Zaman türü|Dosya boyutu türü|
|---------------|---------------|--------------------|
|`_finddata_t`, `_wfinddata_t`|`__time64_t`|`_fsize_t`|
|`_finddata32_t`, `_wfinddata32_t`|`__time32_t`|`_fsize_t`|
|`__finddata64_t`, `__wfinddata64_t`|`__time64_t`|`__int64`|
|`_finddata32i64_t`, `_wfinddata32i64_t`|`__time32_t`|`__int64`|
|`_finddata64i32_t`, `_wfinddata64i32_t`|`__time64_t`|`_fsize_t`|

`_fsize_t` olan bir `typedef` için `unsigned long` (32 bit).

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

## <a name="see-also"></a>Ayrıca bkz.

[Sistem Çağrıları](../c-runtime-library/system-calls.md)
