---
title: _fsopen, _wfsopen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wfsopen
- _fsopen
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
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
dev_langs:
- C++
helpviewer_keywords:
- opening files, streams
- fsopen function
- tfsopen function
- wfsopen function
- _fsopen function
- files [C++], opening
- _tfsopen function
- _wfsopen function
- file sharing [C++]
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a29a81c3430674ddc6d3c04b64fb6dcee3b6a039
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="fsopen-wfsopen"></a>_fsopen, _wfsopen

Bir akış dosya paylaşımı ile açılır.

## <a name="syntax"></a>Sözdizimi

```C
FILE *_fsopen(
   const char *filename,
   const char *mode,
   int shflag
);
FILE *_wfsopen(
   const wchar_t *filename,
   const wchar_t *mode,
   int shflag
);
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Açmak için dosyanın adı.

*Modu*<br/>
İzin verilen erişim türü.

*shflag*<br/>
İzin verilen paylaşım türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir işaretçi akışına döndürür. Null işaretçinin değeri bir hata gösterir. Varsa *filename* veya *modu* olan **NULL** veya boş bir dize açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulama ](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **NULL** ve **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Fsopen** işlev tarafından belirtilen dosyayı açar *filename* bir akış olarak dosyanın sonraki paylaşılan okuma veya yazma modu tarafından tanımlandığı şekilde hazırlar ve *shflag*bağımsız değişkenler. **_wfsopen** bir joker karakter sürümü **_fsopen**; *filename* ve *modu* bağımsız değişkenleri **_wfsopen** olan joker karakter dizeleri. **_wfsopen** ve **_fsopen** Aksi takdirde aynı şekilde davranır.

Karakter dizesi *modu* aşağıdaki tabloda gösterildiği gibi dosya için istenen erişim türünü belirtir.

|Terim|Tanım|
|----------|----------------|
|**"r"**|Okuma için açılır. Dosya yok veya bulunamadı, **_fsopen** çağrısı başarısız olur.|
|**"w"**|Boş bir dosya yazma için açılır. Verilen dosya varsa, içeriği yok.|
|**"a"**|Yazma (ekleme); dosya sonunda açar henüz yoksa dosyayı ilk olarak oluşturur.|
|**"r +"**|Hem okuma ve yazma için açılır. (Dosya var olmalıdır.)|
|**"w +"**|Hem okumak ve yazmak için boş bir dosya açar. Verilen dosya varsa, içeriği yok.|
|**"bir +"**|Okuma ve sonuna ekleme açar; henüz yoksa dosyayı ilk olarak oluşturur.|

Kullanım **"w"** ve **"w +"** var olan dosyaları yok edebilir gibi dikkatli türleri.

Ne zaman bir dosya açıldığında ile **"a"** veya **"bir +"** erişim türüne, tüm işlemleri ortaya dosyanın sonunda yazma. Dosya işaretçisini kullanarak konumlandırılmasına [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md), ancak herhangi bir işlemi gerçekleştirilir yazmadan önce her zaman geri dosyanın sonuna taşınır. Bu nedenle, varolan verilerin üzerine yazılamıyor. Zaman **"r +"**, **"w +"**, veya **"bir +"** erişim türü belirtildi, hem okuma ve yazma izin verilir (dosya güncelleştirmesi açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaparken olmalıdır bir araya giren [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [geri sarma](rewind.md) işlemi. Geçerli konum için belirtilen [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) isterseniz işlemi. Yukarıdaki değerleri ek olarak, şu karakterlerden birini eklenebilir *modu* çeviri modu ve dosya yönetimi yeni satırlar için belirtmek için.

|Terim|Tanım|
|----------|----------------|
|**T**|Bir dosya (çevrilmiş) metin modunda açılır. Bu modda, satır başı satır besleme (CR-LF) birleşimleri girişte tek satır beslemelerini (LF) dönüştürülür ve çıktıyı CR LF birleşimleri için LF karakterleri çevrilir. Ayrıca, CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. Okuma veya okuma/yazma için açılmış dosyalarında **_fsopen** CTRL + Z dosya sonunda olup olmadığını denetler ve, mümkünse kaldırır. Bu kullanılarak yapılır, çünkü [fseek](fseek-fseeki64.md) ve [ftell](ftell-ftelli64.md) CTRL + Z ile biter neden olabilecek bir dosyanın içinde taşımak için [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış bir şekilde davranır.|
|**b**|İkili (untranslated) modda bir dosyayı açar; Yukarıdaki çevirileri görüntülenmez.|
|**S**|Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, sıralı erişim için diskten sınırlı gerekmez olduğunu belirtir.|
|**R**|Önbelleğe alma için en iyi duruma getirilmiş olmakla birlikte, için rasgele erişim diskten sınırlı gerekmez olduğunu belirtir.|
|**T**|Dosya geçici belirtir. Mümkünse, bu değil temizlenip diske.|
|**D**|Dosya geçici belirtir. Son dosya işaretçisini kapatıldığında silinir.|

Varsa **t** veya **b** verilmemiştir *modu*, çeviri modu varsayılan mod değişkeni tarafından tanımlanan **_fmode**. Varsa **t** veya **b** bağımsız değişkeni, işlev başarısız olur ve döndürür önekli **NULL**. Metin ve ikili modlarda tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Bağımsız değişken *shflag* Share.h içinde tanımlanan aşağıdaki bildirim sabitlerden biri oluşan sabit bir ifade.

|Terim|Tanım|
|----------|----------------|
|**_SH_COMPAT**|Uyumluluk modu 16-bit uygulamalar için ayarlar.|
|**_SH_DENYNO**|İzinleri okuma ve yazma erişimi.|
|**_SH_DENYRD**|Dosyaya okuma erişimi engeller.|
|**_SH_DENYRW**|Okuma ve yazma erişimi dosyaya reddeder.|
|**_SH_DENYWR**|Dosyaya yazma erişimini engeller.|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|----------------------|
|**_fsopen**|\<stdio.h >|\<Share.h ><br /><br /> İçin Bildirim sabiti için *shflag* parametresi.|
|**_wfsopen**|\<stdio.h > veya \<wchar.h >|\<Share.h ><br /><br /> İçin Bildirim sabiti için *shflag* parametresi.|

## <a name="example"></a>Örnek

```C
// crt_fsopen.c

#include <stdio.h>
#include <stdlib.h>
#include <share.h>

int main( void )
{
   FILE *stream;

   // Open output file for writing. Using _fsopen allows us to
   // ensure that no one else writes to the file while we are
   // writing to it.
    //
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )
   {
      fprintf( stream, "No one else in the network can write "
                       "to this file until we are done.\n" );
      fclose( stream );
   }
   // Now others can write to the file while we read it.
   system( "type outfile" );
}
```

```Output
No one else in the network can write to this file until we are done.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
