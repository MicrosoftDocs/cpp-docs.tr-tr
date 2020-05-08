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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 379a4adbf17755341fed6a48c649afe29e150fe5
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912121"
---
# <a name="_creat-_wcreat"></a>_creat, _wcreat

Yeni bir dosya oluşturur. **_creat** ve **_wcreat** kullanım dışıdır; Bunun yerine [_sopen_s _wsopen_s](sopen-s-wsopen-s.md) kullanın.

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

Bu işlevler, başarılı olursa oluşturulan dosyaya bir dosya tanımlayıcısı döndürür. Aksi takdirde, işlevler-1 döndürür ve aşağıdaki tabloda gösterildiği gibi **errno** olarak ayarlanır.

|**errno** ayarı|Açıklama|
|---------------------|-----------------|
|**EACCES**|*dosya adı* , var olan bir salt okunurdur veya dosya yerine bir dizin belirtir.|
|**EMFıLE**|Kullanılabilir başka dosya tanımlayıcısı yok.|
|**ENOENT**|Belirtilen dosya bulunamadı.|

*Dosya adı* **null**Ise, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Creat** işlevi yeni bir dosya oluşturur veya var olan bir dosyayı açıp keser. **_wcreat** , **_creat**geniş karakterli bir sürümüdür; _wcreat *dosya adı* bağımsız **_wcreat** değişkeni, geniş karakterli bir dizedir. **_wcreat** ve **_creat** aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

Dosya *adı* tarafından belirtilen dosya yoksa, belirtilen izin ayarıyla yeni bir dosya oluşturulur ve yazma için açılır. Dosya zaten varsa ve izin ayarı yazmaya izin veriyorsa, **_creat** dosyayı 0 uzunluğuna kırpar, önceki içerikleri yok edin ve yazmak için açar. İzin ayarı, *pmode*, yalnızca yeni oluşturulan dosyalar için geçerlidir. Yeni dosya, ilk kez kapatıldıktan sonra belirtilen izin ayarını alır. *Pmode* tamsayı ifadesi bir veya her ikisini de **_S_IWRITE** , SYS\Stat.exe içinde tanımlanan bildirim sabitlerinden birini ya da **_S_IREAD**içerir. Her iki sabit de verildiğinde, bit düzeyinde OR işleci ( **&#124;** ) ile birleştirilir. *Pmode* parametresi aşağıdaki değerlerden birine ayarlanır.

|Değer|Tanım|
|-----------|----------------|
|**_S_IWRITE**|Yazma izni veriliyor.|
|**_S_IREAD**|Okuma izni verildi.|
|**_S_IREAD** &#124; **_S_IWRITE**|Okuma ve yazma izni verildi.|

Yazma izni verilmezse, dosya salt okunurdur. Tüm dosyalar her zaman okunabilir; salt yazılır izin vermek olanaksızdır. **_S_IWRITE** ve **_S_IREAD** | **_S_IWRITE** modları eşdeğerdir. **_Creat** kullanılarak açılan dosyalar her zaman uyumluluk modunda açılır (bkz. [_sopen](sopen-wsopen.md)) **_SH_DENYNO**.

**_creat** , izinleri ayarlamadan önce geçerli dosya izni maskesini *pmode* 'a uygular (bkz. [_umask](umask.md)). **_creat** öncelikle önceki kitaplıklarla uyumluluk için sağlanır. *Oflag* parametresindeki **_O_CREAT** ve **_O_TRUNC** ile **_open** çağrısı **_creat** eşdeğerdir ve yeni kod için tercih edilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_creat**|\<GÇ. h>|\<sys/Types. h>, \<sys/stat. h>, \<errno. h>|
|**_wcreat**|\<GÇ. h> veya \<wchar. h>|\<sys/Types. h>, \<sys/stat. h>, \<errno. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Alt düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
