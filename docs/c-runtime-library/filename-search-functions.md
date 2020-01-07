---
title: Dosya adı arama Işlevleri
ms.date: 11/04/2016
api_location:
- msvcr100.dll
- msvcr120.dll
- msvcr90.dll
- msvcrt.dll
- msvcr80.dll
- msvcr110.dll
- msvcr110_clr0400.dll
api_type:
- DLLExport
topic_type:
- apiref
helpviewer_keywords:
- file names [C++], searching for
- _find function
- wfind function
- find function
- _wfind function
ms.assetid: 2bc2f8ef-44e4-4271-b3e8-666d36fde828
ms.openlocfilehash: 331d43f3e3a88786f8dac0a6f609f988beea9dbb
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75300319"
---
# <a name="filename-search-functions"></a>Dosya adı arama Işlevleri

Bu işlevler, belirtilen dosya adları için aramaları arar ve kapatır:

- [_findnext, _wfindnext](../c-runtime-library/reference/findnext-functions.md)

- [_findfirst, _wfindfirst](../c-runtime-library/reference/findfirst-functions.md)

- [_findclose](../c-runtime-library/reference/findclose.md)

## <a name="remarks"></a>Açıklamalar

`_findfirst` işlevi, `filespec` bağımsız değişkeninde belirtilen dosyayla eşleşen bir dosya adının ilk örneğiyle ilgili bilgiler sağlar. ' De, ana bilgisayar işletim sistemi tarafından desteklenen herhangi bir joker karakter bileşimini `filespec` kullanabilirsiniz.

İşlevler, GÇ. h içinde tanımlanan `_finddata_t` yapıda dosya bilgileri döndürür. Ailedeki çeşitli işlevler `_finddata_t` yapısında birçok çeşitlemeyi kullanır. Temel `_finddata_t` yapısı aşağıdaki öğeleri içerir:

`unsigned attrib`<br/>
Dosya özniteliği.

`time_t time_create`<br/>
Dosya oluşturma zamanı (FAT dosya sistemleri için-1L). Bu süre UTC biçiminde depolanır. Yerel saate dönüştürmek için [localtime_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)kullanın.

`time_t time_access`<br/>
Son dosya erişiminin saati (FAT dosya sistemleri için-1L). Bu süre UTC biçiminde depolanır. Yerel saate dönüştürmek için `localtime_s`kullanın.

`time_t time_write`<br/>
Dosyanın son yazma zamanı. Bu süre UTC biçiminde depolanır. Yerel saate dönüştürmek için `localtime_s`kullanın.

`_fsize_t size`<br/>
Dosyanın bayt cinsinden uzunluğu.

`char name`[`_MAX_PATH`] eşleşen dosya veya dizinin null ile sonlandırılmış adı, yol olmadan.

FAT sistemi gibi bir dosyanın oluşturma ve son erişim zamanlarını desteklemeyen dosya sistemlerinde, `time_create` ve `time_access` alanları her zaman-1L ' dir.

`_MAX_PATH`, Stdlib. h 'de 260 bayt olarak tanımlanmıştır.

Bulma işlemini sınırlandırmak için hedef öznitelikleri (örneğin, `_A_RDONLY`) belirtemezsiniz. Bu öznitelikler, `_finddata_t` yapısının `attrib` alanında döndürülür ve aşağıdaki değerlere sahip olabilir (GÇ. h içinde tanımlanmıştır). Kullanıcılar, `attrib` alanı için mümkün olan tek değerler olmamalıdır.

`_A_ARCH`<br/>
Arşivliyorsanız. Dosya her değiştirildiğinde ve **yedekleme** komutu tarafından temizlendiğinde ayarlanır. Değer: 0x20.

`_A_HIDDEN`<br/>
Gizli dosya. **/Ah** seçeneğini kullanmadığınız müddetçe, genellikle dır komutuyla birlikte görünmez. Bu özniteliğe sahip normal dosyalar ve dosyalar hakkında bilgi döndürür. Değer: 0x02.

`_A_NORMAL`<br/>
Olağan. Dosya başka bir özniteliğe ayarlı değil ve kısıtlama olmadan okunabilir veya yazılabilir. Değer: 0x00.

`_A_RDONLY`<br/>
Salt okunur. Dosya yazma için açılamıyor ve aynı ada sahip bir dosya oluşturulamıyor. Değer: 0x01.

`_A_SUBDIR`<br/>
Dizin. Değer: 0x10.

`_A_SYSTEM`<br/>
Sistem dosyası. **/A** veya **/a: S** seçeneği kullanılmamışsa normalde **dır** komutuyla görünmez. Değer: 0x04.

`_findnext`, varsa, daha önceki `_findfirst`çağrısında belirtilen `filespec` bağımsız değişkeniyle eşleşen bir sonraki adı bulur. `fileinfo` bağımsız değişkeni, önceki `_findfirst`çağrısıyla başlatılan bir yapıya işaret etmelidir. Bir eşleşme bulunursa `fileinfo` yapısı içerikleri daha önce açıklandığı gibi değiştirilir. Aksi takdirde, değiştirilmez. `_findclose`, belirtilen arama tutamacını kapatır ve hem `_findfirst` hem de `_findnext`ilişkili tüm kaynakları yayınlar. `_findfirst` ya da `_findnext` tarafından döndürülen tanıtıcı,, silme gibi değişiklik işlemleri, bunlara geçirilen yolları oluşturan dizinlerde gerçekleştirilebilecek şekilde önce `_findclose`geçirilmelidir.

`_find` işlevlerini iç içe geçirebilirsiniz. Örneğin, `_findfirst` veya `_findnext` çağrısı bir alt dizin olan dosyayı bulursa, başka bir `_findfirst` veya `_findnext`çağrısıyla yeni bir arama başlatılabilir.

`_wfindfirst` ve `_wfindnext`, `_findfirst` ve `_findnext`'ın geniş karakterli sürümleridir. Geniş karakterli sürümlerin yapı bağımsız değişkeni, GÇ. h içinde ve wchar. h içinde tanımlanan `_wfinddata_t` veri türüne sahiptir. Bu veri türü alanları, `_wfinddata_t` ad alanı `char`türü yerine `wchar_t` türünde olması dışında `_finddata_t` veri türüyle aynıdır. Aksi takdirde `_wfindfirst` ve `_wfindnext` `_findfirst` ve `_findnext`aynı şekilde davranır.

`_findfirst` ve `_findnext` 64 bit zaman türünü kullanır. Eski 32 bit zaman türünü kullanmanız gerekiyorsa `_USE_32BIT_TIME_T`tanımlayabilirsiniz. Adlarında `32` sonekine sahip bu işlevlerin sürümleri 32 bitlik saat türünü kullanır ve `64` sonekine sahip olanlar 64 bit zaman türünü kullanır.

`_findfirst32i64`, `_findnext32i64`, `_wfindfirst32i64`ve `_wfindnext32i64` işlevleri, kullandıkları ve 64 bit dosya uzunluklarının döndürdüğü durumlar hariç, bu işlevlerin 32 bitlik zaman türü sürümleriyle aynı şekilde davranır. İşlevler `_findfirst64i32`, `_findnext64i32`, `_wfindfirst64i32`ve `_wfindnext64i32` 64 bit zaman türünü kullanır, ancak 32 bit dosya uzunluklarını kullanır. Bu işlevler, zaman ve dosya boyutu için alanların farklı türlerine sahip olduğu `_finddata_t` türünün uygun çeşitlemelerini kullanır.

`_finddata_t`, aslında `_finddata64i32_t` değerlendirilen bir makrodur (veya `_USE_32BIT_TIME_T` tanımlanmışsa `_finddata32_t`). Aşağıdaki tabloda `_finddata_t`çeşitlemeleri özetlenmektedir:

|Yapı|Zaman türü|Dosya boyutu türü|
|---------------|---------------|--------------------|
|`_finddata_t`, `_wfinddata_t`|`__time64_t`|`_fsize_t`|
|`_finddata32_t`, `_wfinddata32_t`|`__time32_t`|`_fsize_t`|
|`__finddata64_t`, `__wfinddata64_t`|`__time64_t`|`__int64`|
|`_finddata32i64_t`, `_wfinddata32i64_t`|`__time32_t`|`__int64`|
|`_finddata64i32_t`, `_wfinddata64i32_t`|`__time64_t`|`_fsize_t`|

`_fsize_t`, `unsigned long` için bir `typedef` (32 bit).

## <a name="example"></a>Örnek

```c
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
