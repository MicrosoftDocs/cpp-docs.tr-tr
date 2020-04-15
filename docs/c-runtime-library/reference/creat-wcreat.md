---
title: _creat, _wcreat
ms.date: 4/2/2020
api_name:
- _creat
- _wcreat
- _o__creat
- _o__wcreat
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
ms.openlocfilehash: 18ecf78d2cbff3647eae912a1bb1b17d5340f185
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348333"
---
# <a name="_creat-_wcreat"></a>_creat, _wcreat

Yeni bir dosya oluşturur. **_creat** ve **_wcreat** küçümsülmüyor; [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) kullanın.

## <a name="syntax"></a>Sözdizimi

```C
int _creat(
   const char *filename,
   int pmode
);
int _wcreat(
   const wchar_t *filename,
   int pmode
);
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Yeni dosyanın adı.

*pmode*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler, başarılı olursa, oluşturulan dosyaya bir dosya tanımlayıcısı döndürür. Aksi takdirde, işlevler -1 döndürdü ve aşağıdaki tabloda gösterildiği gibi **errno** ayarlayın.

|**errno** ayarı|Açıklama|
|---------------------|-----------------|
|**EACCES**|*dosya adı* varolan salt okunur dosyayı belirtir veya dosya yerine bir dizin belirtir.|
|**EMFILE**|Başka dosya tanımlayıcısı yok.|
|**Enoent**|Belirtilen dosya bulunamadı.|

*Dosya adı* **NULL**ise, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** ve return -1 **için errno** ayarlayın.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_creat** işlevi yeni bir dosya oluşturur veya varolan bir dosyayı açar ve keser. **_wcreat** **_creat**geniş karakterli bir versiyonudur; **_wcreat** için *dosya adı* bağımsız değişkeni geniş karakterli bir dizedir. **_wcreat** ve **_creat** aynı şekilde aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

*Dosya adı* ile belirtilen dosya yoksa, verilen izin ayarı ile yeni bir dosya oluşturulur ve yazı için açılır. Dosya zaten varsa ve izin ayarı yazmaya izin veriyorsa, **_creat** dosyayı 0 uzunluğa küçültür, önceki içeriği yok eder ve yazmak için açar. İzin ayarı, *pmode,* yalnızca yeni oluşturulan dosyalar için geçerlidir. Yeni dosya, ilk kez kapatıldıktan sonra belirtilen izin ayarını alır. Tamsayı ifade *pmode* bir veya her ikisi **de** _S_IWRITE ve **_S_IREAD,** SYS\Stat.h tanımlanan gösterir sabitleri içerir. Her iki sabit de verildiğinde, bitwise veya işleç **(&#124;)** ile birleştirilir. *Pmode* parametresi aşağıdaki değerlerden birine ayarlanır.

|Değer|Tanım|
|-----------|----------------|
|**_S_IWRITE**|Yazmaya izin verilir.|
|**_S_IREAD**|Okumaya izin verilir.|
|**_S_IREAD** &#124; **_S_IWRITE**|Okuma ve yazmaya izin verilir.|

Yazma izni verilmezse, dosya salt okunur. Tüm dosyalar her zaman okunabilir; yalnızca yazma izni vermek mümkün değildir. _S_IWRITE ve **_S_IREAD** | **_S_IWRITE** **modları** daha sonra eşdeğerdir. **_creat** kullanılarak açılan dosyalar her zaman uyumluluk modunda açılır [(_sopen](sopen-wsopen.md)bakınız) **_SH_DENYNO.**

**_creat,** izinleri ayarlamadan önce geçerli dosya izni maskesini *pmode'e* uygular (bkz. [_umask).](umask.md) **_creat** öncelikle önceki kitaplıklarla uyumluluk için sağlanır. *Oflag* parametresi _O_CREAT **ve** **_O_TRUNC** ile **_open** için yapılan **arama, _creat** eşdeğerdir ve yeni kod için tercih edilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h>|\<sys/types.h>, \<sys/stat.h \<>, errno.h>|
|**_wcreat**|\<io.h> \<veya wchar.h>|\<sys/types.h>, \<sys/stat.h \<>, errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_creat.c
// compile with: /W3
// This program uses _creat to create
// the file (or truncate the existing file)
// named data and open it for writing.

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   int fh;

   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996
   // Note: _creat is deprecated; use _sopen_s instead
   if( fh == -1 )
      perror( "Couldn't create data file" );
   else
   {
      printf( "Created data file.\n" );
      _close( fh );
   }
}
```

```Output
Created data file.
```

## <a name="see-also"></a>Ayrıca bkz.

[Düşük Seviyeli G/Ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
