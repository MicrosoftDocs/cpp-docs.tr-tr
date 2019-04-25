---
title: _fsopen, _wfsopen
ms.date: 11/04/2016
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
ms.openlocfilehash: 197a4f690a6626edbfec27ea4abef1999b6cedaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287713"
---
# <a name="fsopen-wfsopen"></a>_fsopen, _wfsopen

Bir akışı, dosya paylaşımı ile açılır.

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

Bu işlevlerin her biri, akışa bir işaretçi döndürür. Bir null işaretçi değeri bir hata olduğunu gösterir. Varsa *filename* veya *modu* olduğu **NULL** ya da boş bir dize içinde açıklanan şekilde bu işlevler geçersiz parametre işleyicisi çağırır [parametre doğrulama ](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **NULL** ayarlayıp **errno** için **EINVAL**.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Fsopen** işlevi tarafından belirtilen dosyayı açar *filename* bir akış olarak dosya sonraki paylaşılan okuma veya yazma modu tarafından tanımlandığı şekilde hazırlar ve *shflag*bağımsız değişkenler. **_wfsopen** geniş karakterli sürümüdür **_fsopen**; *filename* ve *modu* bağımsız değişkenleri **_wfsopen** olan geniş karakterli dizelerdir. **_wfsopen** ve **_fsopen** aynı şekilde davranır.

Karakter dizesi *modu* aşağıdaki tabloda gösterildiği gibi dosya için istenen erişim türünü belirtir.

|Terim|Tanım|
|----------|----------------|
|**"r"**|Okuma için açar. Dosya mevcut değil ya da bulunamıyorsa **_fsopen** çağrısı başarısız olur.|
|**"w"**|Yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir.|
|**"a"**|(Ekleme); dosyanın sonunda yazma için açar henüz yoksa, dosyayı ilk oluşturur.|
|**"r +"**|Hem okuma ve yazma için açar. (Dosya var olmalıdır.)|
|**"w +"**|Hem okuma ve yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir.|
|**"a+"**|Okuma ve ekleme için açar; henüz yoksa, dosyayı ilk oluşturur.|

Kullanım **"w"** ve **"w +"** türleri dikkatli olarak var olan dosyaları yok edebilir.

Ne zaman bir dosya açıldığında ile **"a"** veya **"a +"** erişim türü, tüm yazma işlemleri dosyanın sonunda gerçekleşir. Dosya işaretçisi kullanılarak konumlandırılabilir [fseek](fseek-fseeki64.md) veya [rewind](rewind.md), ancak herhangi bir işlemi yazma önce her zaman geri dosyanın sonuna kadar taşınır. Bu nedenle, var olan verilerin üzerine yazılamaz. Zaman **"r +"**, **"w +"**, veya **"a +"** erişim türü belirtildiğinde, hem okumaya hem yazmaya izin verilir (dosyanın güncelleştirme için açık olarak kabul edilir). Ancak, yazma ve okuma arasında geçiş yaparken olmalıdır bir araya giren [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [rewind](rewind.md) işlemi. Geçerli konum için belirtilen [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) isterseniz işlemi. Yukarıdaki değerlerden ek olarak, şu karakterlerden birini eklenebilir *modu* dosya yönetimi ve yeni satırlar için çeviri modunu belirtmek için.

|Terim|Tanım|
|----------|----------------|
|**T**|Metin (çevrilmiş) modunda bir dosya açar. Bu modda, satır başı satır besleme (CR-LF) kombinasyonları girişte tek satır beslemelerini (LF) çevrilir ve LF karakterleri için çıkış CR-LF kombinasyonlarına çevrilir. Ayrıca, CTRL + Z girişteki bir dosya sonu karakteri olarak yorumlanır. Okuma veya okuma/yazma için açılmış dosyalarında **_fsopen** CTRL + Z dosya sonunda olup olmadığını denetler ve eğer mümkünse bunu kaldırır. Kullanıldığından yapıldığını [fseek](fseek-fseeki64.md) ve [ftell](ftell-ftelli64.md) CTRL + Z ile biter neden olabilecek bir dosya içinde hareket etmek [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış davranmasına.|
|**b**|İkili (çevrilmemiş) modda bir dosyayı açar; Yukarıdaki Çeviriler bastırılır.|
|**S**|Önbelleğe alma iyileştirildiğini, ancak sıralı erişim için diskten sınırlı olduğunu belirtir.|
|**R**|Önbelleğe alma iyileştirildiğini, ancak rastgele erişim için diskten sınırlı olduğunu belirtir.|
|**T**|Bir dosyayı geçici olarak belirtir. Mümkünse, boşaltılmaz diske.|
|**D**|Bir dosyayı geçici olarak belirtir. Son dosya işaretçisi kapatıldığında silinir.|

Varsa **t** veya **b** verilmez *modu*, çeviri modu varsayılan modlu değişkeni tarafından tanımlanan **_fmode**. Varsa **t** veya **b** bağımsız değişken, işlev başarısız olur ve döndürür önekli **NULL**. Metin ve ikili modlarının bir tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

Bağımsız değişken *shflag* Share.h içinde tanımlanan aşağıdaki bildirim sabitlerinden birini içeren sabit bir ifade.

|Terim|Tanım|
|----------|----------------|
|**_SH_COMPAT**|16-bit uygulamalar için Uyumluluk modu ayarlar.|
|**_SH_DENYNO**|İzin verir, okuma ve yazma erişimi.|
|**_SH_DENYRD**|Dosya okuma erişimi engeller.|
|**_SH_DENYRW**|Okuma ve dosyaya yazma erişimi engeller.|
|**_SH_DENYWR**|Dosya yazma erişimi engeller.|

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üst bilgiler|
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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
