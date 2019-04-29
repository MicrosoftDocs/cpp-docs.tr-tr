---
title: _creat, _wcreat
ms.date: 11/04/2016
apiname:
- _creat
- _wcreat
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 901a95a6a9361f95f38749dacf1a5001d97b3761
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335314"
---
# <a name="creat-wcreat"></a>_creat, _wcreat

Yeni bir dosya oluşturur. **_creat** ve **_wcreat** kullanın; kullanımdan kaldırılan [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) yerine.

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

*Dosya adı*<br/>
Yeni dosyanın adı.

*pmode*<br/>
İzin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler, başarılı olursa, oluşturulan dosyanın dosya tanımlayıcısını döndürür. Aksi takdirde, İşlevler -1 döndürür ve **errno** aşağıdaki tabloda gösterildiği gibi.

|**errno** ayarı|Açıklama|
|---------------------|-----------------|
|**SPAWN**|*filename* var olan bir salt okunur dosya veya dizin dosyası belirtir.|
|**EMFILE**|Daha fazla hiçbir dosya tanımlayıcısı kullanılabilir.|
|**ENOENT**|Belirtilen dosya bulunamadı.|

Varsa *filename* olduğu **NULL**, açıklandığı gibi bu işlevler geçersiz parametre işleyicisini çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Creat** işlevi yeni bir dosya oluşturur veya açılır ve var olan bir keser. **_wcreat** geniş karakterli sürümüdür **_creat**; *filename* bağımsız değişkeni **_wcreat** geniş karakterli bir dizedir. **_wcreat** ve **_creat** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

Dosya belirtilen *filename* yok, yeni bir dosya ile verilen izin ayarının oluşturulur ve yazma için açılmış. Dosya zaten var ve kendi izin ayarı yazmaya sağlar **_creat** önceki içeriği yok etme uzunluğu 0 dosyasına keser ve yazma için açar. İzin ayarının *pmode*, yalnızca yeni oluşturulan dosyalar için geçerlidir. İlk kez kapatıldıktan sonra yeni dosyayı belirtilen izin ayarını alır. Tamsayı ifadesini *pmode* birini veya ikisini de bildirim sabitleri içeren **_s_ıwrıte** ve **_s_ıread**SYS\Stat.h içinde tanımlanmış. Her iki sabitleri verildiğinde, bunlar ile bit düzeyinde birleştirilir veya işleci ( **&#124;** ). *Pmode* parametre aşağıdaki değerlerden birine ayarlanır.

|Değer|Tanım|
|-----------|----------------|
|**_S_IWRITE**|Yazma izin verilir.|
|**_S_IREAD**|Okuma izin verilir.|
|**_S_IREAD** &#124; **_S_IWRITE**|Okuma ve yazma izin verilir.|

Yazma izni verilmemişse, dosyanın salt okunur. Tüm dosyaları her zaman okunabilir; Salt yazma izni vermek mümkün değildir. Modları **_s_ıwrıte** ve **_s_ıread** | **_s_ıwrıte** ardından eşdeğerdir. Kullanarak açılan dosyaları **_creat** her zaman uyumluluk modunda açılan (bkz [_sopen](sopen-wsopen.md)) ile **_SH_DENYNO**.

**_creat** geçerli dosya izni maskesi geçerli *pmode* izinleri ayarlamadan önce (bkz [_umask](umask.md)). **_creat** öncelikle önceki kitaplıkları ile uyumluluk için sağlanır. Bir çağrı **_aç** ile **_O_CREAT** ve **_O_TRUNC** içinde *oflag* parametredir eşdeğer **_creat**ve yeni kod için tercih edilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|
|**_wcreat**|\<io.h > veya \<wchar.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|

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

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)<br/>
[_chmod, _wchmod](chmod-wchmod.md)<br/>
[_chsize](chsize.md)<br/>
[_close](close.md)<br/>
[_dup, _dup2](dup-dup2.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
[_umask](umask.md)<br/>
