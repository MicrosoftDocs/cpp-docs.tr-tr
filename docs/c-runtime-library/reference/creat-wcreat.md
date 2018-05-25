---
title: _creat, _wcreat | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a6b987faa30439f0f374838fe7fcd4d942b8cc7
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
---
# <a name="creat-wcreat"></a>_creat, _wcreat

Yeni bir dosya oluşturur. **_creat** ve **_wcreat** kullanım dışı bırakıldı; kullanın [_sopen_s, _wsopen_s](sopen-s-wsopen-s.md) yerine.

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
Yeni dosya adı.

*pmode*<br/>
İzni ayarı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler başarılı olursa, oluşturulan dosya için dosya tanımlayıcısı döndürür. Aksi takdirde işlevleri -1 döndürür ve **errno** aşağıdaki tabloda gösterildiği gibi.

|**errno** ayarı|Açıklama|
|---------------------|-----------------|
|**EACCES**|*filename* varolan salt okunur dosyanın veya bir dosya yerine bir dizin belirtir.|
|**EMFILE**|Daha fazla hiçbir dosya tanımlayıcıları kullanılabilir.|
|**ENOENT**|Belirtilen dosya bulunamadı.|

Varsa *filename* olan **NULL**, bu işlevler açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Creat** işlevi yeni bir dosya oluşturur veya açar ve mevcut bir tamsayıya dönüştürür. **_wcreat** bir joker karakter sürümü **_creat**; *filename* bağımsız değişkeni **_wcreat** bir joker karakter dizesidir. **_wcreat** ve **_creat** Aksi takdirde aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcreat**|**_creat**|**_creat**|**_wcreat**|

Dosyanın belirtilen *filename* mevcut olmadığından yeni bir dosya ile verilen izni ayarı oluşturulur ve yazma için açılmış. Dosya zaten varsa ve yazma izni ayarı sağlar **_creat** önceki içeriği yok etme uzunluğu 0, dosyaya tamsayıya dönüştürür ve yazma için açar. İzni ayarı *pmode*, yalnızca yeni oluşturulan dosyalar için geçerlidir. İlk kez kapatıldıktan sonra yeni dosya belirtilen izin ayarını alır. Tamsayı ifade *pmode* birini veya her ikisini bildirim sabitleri içerir **_s_ıwrıte** ve **_s_ıread**, SYS\Stat.h içinde tanımlı. Her iki sabitleri verildiğinde, bunlar Bitsel ile birleştirilir veya işleci ( **&#124;** ). *Pmode* parametresi şu değerlerden biri olarak ayarlanır.

|Değer|Tanım|
|-----------|----------------|
|**_S_IWRITE**|Yazma izin verilir.|
|**_S_IREAD**|Okuma izin verilir.|
|**_S_IREAD** &AMP;#124; **_S_IWRITE**|Okuma ve yazma izin verilir.|

Yazma izni verilmedi, dosya salt okunurdur. Tüm dosyaları her zaman okunabilir; salt yazılır izin vermek mümkün değildir. Modları **_s_ıwrıte** ve **_s_ıread** | **_s_ıwrıte** sonra eşdeğerdir. Kullanarak açılan dosyaları **_creat** her zaman uyumluluk modunda açılmış (bkz [_sopen](sopen-wsopen.md)) ile **_SH_DENYNO**.

**_creat** geçerli dosya izni maskesi uygular *pmode* izinleri ayarlamadan önce (bkz [_umask](umask.md)). **_creat** öncelikle önceki kitaplıkları ile uyumluluk için sağlanır. Çağrı **_kurulum Aç** ile **_O_CREAT** ve **_O_TRUNC** içinde *oflag* parametredir eşdeğer **_creat**ve için yeni kod tercih edilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_creat**|\<io.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|
|**_wcreat**|\<io.h > veya \<wchar.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
