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
ms.openlocfilehash: ecc01362bdc14af32df5093ad1ac1ee606026d8f
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940374"
---
# <a name="filename-search-functions"></a>Dosya adı arama Işlevleri

Bu işlevler, belirtilen dosya adları için aramaları arar ve kapatır:

- [_sonrakinibul, _wsonra](../c-runtime-library/reference/findnext-functions.md)

- [_findfirst, _wfindfirst](../c-runtime-library/reference/findfirst-functions.md)

- [_findclose](../c-runtime-library/reference/findclose.md)

## <a name="remarks"></a>Açıklamalar

İşlevi, `filespec` bağımsız değişkeninde belirtilen dosyayla eşleşen bir dosya adının ilk örneğiyle ilgili bilgiler sağlar. `_findfirst` Ana bilgisayar işletim sistemi `filespec` tarafından desteklenen herhangi bir joker karakter birleşimini kullanabilirsiniz.

İşlevler, GÇ. h içinde tanımlanan `_finddata_t` bir yapıda dosya bilgileri döndürür. Ailedeki çeşitli işlevler, `_finddata_t` yapı üzerinde birçok çeşitlemeyi kullanır. Temel `_finddata_t` yapı aşağıdaki öğeleri içerir:

`unsigned attrib`<br/>
Dosya özniteliği.

`time_t time_create`<br/>
Dosya oluşturma zamanı (FAT dosya sistemleri için-1L). Bu süre UTC biçiminde depolanır. Yerel saate dönüştürmek için [localtime_s](../c-runtime-library/reference/localtime-s-localtime32-s-localtime64-s.md)kullanın.

`time_t time_access`<br/>
Son dosya erişiminin saati (FAT dosya sistemleri için-1L). Bu süre UTC biçiminde depolanır. Yerel saate dönüştürmek için kullanın `localtime_s`.

`time_t time_write`<br/>
Dosyanın son yazma zamanı. Bu süre UTC biçiminde depolanır. Yerel saate dönüştürmek için kullanın `localtime_s`.

`_fsize_t size`<br/>
Dosyanın bayt cinsinden uzunluğu.

`char name`[ `_MAX_PATH`] Yol olmadan eşleşen dosya veya dizinin null ile sonlandırılmış adı.

FAT sistemi gibi bir dosyanın oluşturma ve son erişim zamanlarını desteklemeyen dosya sistemlerinde, `time_create` ve `time_access` alanları her zaman-1L ' dir.

`_MAX_PATH`, Stdlib. h 'de 260 bayt olarak tanımlanmıştır.

Bulma işlemini sınırlandırmak için hedef öznitelikleri ( `_A_RDONLY`gibi) belirtemezsiniz. Bu öznitelikler, `attrib` `_finddata_t` yapının alanında döndürülür ve aşağıdaki değerlere sahip olabilir (GÇ. h içinde tanımlanmıştır). Kullanıcılar, `attrib` alan için mümkün olan tek değerleri değil, bunlara güvenmemelidir.

`_A_ARCH`<br/>
Arşivliyorsanız. Dosya her değiştirildiğinde ve **yedekleme** komutu tarafından temizlendiğinde ayarlanır. Deeri 0x20.

`_A_HIDDEN`<br/>
Gizli dosya. **/Ah** seçeneğini kullanmadığınız müddetçe, genellikle dır komutuyla birlikte görünmez. Bu özniteliğe sahip normal dosyalar ve dosyalar hakkında bilgi döndürür. Deeri 0x02 şeklindedir.

`_A_NORMAL`<br/>
Olağan. Dosya başka bir özniteliğe ayarlı değil ve kısıtlama olmadan okunabilir veya yazılabilir. Deeri -.

`_A_RDONLY`<br/>
Salt okunur. Dosya yazma için açılamıyor ve aynı ada sahip bir dosya oluşturulamıyor. Deeri 0x01.

`_A_SUBDIR`<br/>
Dizin. Deeri 0x10.

`_A_SYSTEM`<br/>
Sistem dosyası. **/A** veya **/a: S** seçeneği kullanılmamışsa normalde **dır** komutuyla görünmez. Deeri 0x04.

`_findnext`daha önceki bir `filespec` `_findfirst`çağrısında belirtilen bağımsız değişkenle eşleşen bir sonraki adı bulur. Bağımsız değişkeni, önceki `_findfirst`çağrısıyla başlatılan bir yapıya işaret etmelidir. `fileinfo` Bir eşleşme bulunursa, `fileinfo` yapı içerikleri daha önce açıklandığı gibi değiştirilir. Aksi takdirde, değiştirilmez. `_findclose`Belirtilen arama tutamacını kapatır ve hem hem de `_findfirst` `_findnext`tüm ilişkili kaynakları serbest bırakır. Ya da `_findfirst` `_findnext` önce tarafındandöndürülentanıtıcı,silmegibideğişiklikişlemleri,bunlarageçirilenyollarıoluşturandizinlerdegerçekleştirilebilir.`_findclose`

`_find` İşlevleri iç içe geçirebilirsiniz. Örneğin, bir alt dizin olan dosyasına `_findfirst` bir `_findnext` çağrı veya dosya bulunursa yeni bir arama, veya `_findnext`için `_findfirst` başka bir çağrısıyla başlatılabilir.

`_wfindfirst`ve, `_findfirst` ve`_findnext`öğesinin geniş karakterli sürümleridir. `_wfindnext` Geniş karakterli sürümlerin yapı bağımsız değişkeni, GÇ. h içinde `_wfinddata_t` ve wchar. h içinde tanımlanan veri türüne sahiptir. Bu veri `_finddata_t` türü alanları, veri türüyle aynıdır, ancak `_wfinddata_t` ad alanı tür `char`yerine tür `wchar_t` olur. Aksi takdirde `_wfindfirst` ve `_findfirst` ile aynışekildedavranır.`_findnext` `_wfindnext`

`_findfirst`ve `_findnext` 64 bitlik saat türünü kullanın. Eski 32 bit zaman türünü kullanmanız gerekiyorsa tanımlayabilir `_USE_32BIT_TIME_T`. Adlarında `32` sonekine sahip bu işlevlerin sürümleri 32 bitlik saat türünü kullanır ve `64` sonekine sahip olanlar 64 bit zaman türünü kullanır.

, `_findfirst32i64`, `_findnext32i64`Ve işlevleri`_wfindnext32i64` , kullandıkları ve 64 bit dosya uzunluklarının döndürdüğü durumlar hariç, bu işlevlerin 32 bitlik zaman türü sürümleriyle aynı şekilde davranır. `_wfindfirst32i64` , `_findfirst64i32`, `_findnext64i32`, `_wfindfirst64i32`Ve işlevleri`_wfindnext64i32` 64 bitlik saat türünü kullanır, ancak 32 bit dosya uzunluklarını kullanır. Bu işlevler, zaman ve dosya boyutu `_finddata_t` için alanların farklı türlerine sahip olduğu türün uygun çeşitlemelerini kullanır.

`_finddata_t`Aslında `_finddata64i32_t` `_finddata32_t` (`_USE_32BIT_TIME_T` veya tanımlanmışsa) sonucunu veren bir makrodur. Aşağıdaki tabloda üzerinde `_finddata_t`Çeşitlemeler özetlenmektedir:

|Yapı|Zaman türü|Dosya boyutu türü|
|---------------|---------------|--------------------|
|`_finddata_t`, `_wfinddata_t`|`__time64_t`|`_fsize_t`|
|`_finddata32_t`, `_wfinddata32_t`|`__time32_t`|`_fsize_t`|
|`__finddata64_t`, `__wfinddata64_t`|`__time64_t`|`__int64`|
|`_finddata32i64_t`, `_wfinddata32i64_t`|`__time32_t`|`__int64`|
|`_finddata64i32_t`, `_wfinddata64i32_t`|`__time64_t`|`_fsize_t`|

`_fsize_t`, için `typedef` `unsigned long` bir (32 bit).

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
