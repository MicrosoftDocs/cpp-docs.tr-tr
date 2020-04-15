---
title: _fsopen, _wfsopen
ms.date: 4/2/2020
api_name:
- _wfsopen
- _fsopen
- _o__fsopen
- _o__wfsopen
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
ms.openlocfilehash: 49907808729375e3bea18a5f4bbf204852e0072a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345694"
---
# <a name="_fsopen-_wfsopen"></a>_fsopen, _wfsopen

Dosya paylaşımı yla bir akış açar.

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

*filename*<br/>
Açılacak dosyanın adı.

*Modu*<br/>
Erişim türüne izin verilir.

*shflag*<br/>
İzin verilen paylaşım türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri akışa bir işaretçi döndürür. Null işaretçi değeri bir hata gösterir. *Dosya adı* veya *mod* **NULL** veya boş bir dize ise, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütme devam etmesine izin verilirse, bu işlevler **NULL** döndürdü ve **EINVAL** **için errno** ayarlayın.

Bu ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**_fsopen** *işlevi, dosya adı* tarafından belirtilen dosyayı akış olarak açar ve dosyayı mod tarafından tanımlandığı şekilde sonraki paylaşılan okuma veya yazmaya hazırlar ve bağımsız *değişkenleri küçülter.* **_wfsopen** **_fsopen**geniş karakterli bir versiyonudur; **_wfsopen** için *dosya adı* ve *mod* bağımsız değişkenleri geniş karakterdizeleridir. **_wfsopen** ve **_fsopen** aynı şekilde davranan.

Karakter dize *modu,* aşağıdaki tabloda gösterildiği gibi dosya için istenen erişim türünü belirtir.

|Sözleşme Dönemi|Tanım|
|----------|----------------|
|**"r"**|Okumak için açılır. Dosya yoksa veya bulunamıyorsa, **_fsopen** arama başarısız olur.|
|**"w"**|Yazmak için boş bir dosya yı açar. Verilen dosya varsa, içeriği yok edilir.|
|**"a"**|Dosyanın sonunda (ek olarak) yazı için açılır; yoksa önce dosyayı oluşturur.|
|**"r+"**|Hem okuma hem de yazma için açılır. (Dosya bulunmalıdır.)|
|**"w+"**|Hem okuma hem de yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir.|
|**"a+"**|Okuma ve ekolarak açılır; yoksa önce dosyayı oluşturur.|

Varolan dosyaları yok edebileceğinden, **"w"** ve **"w+"** türlerini dikkatli kullanın.

Bir dosya **"a" veya "a+"** erişim türüyle açıldığında, tüm yazma işlemleri dosyanın sonunda gerçekleşir. **"a+"** Dosya işaretçisi [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak herhangi bir yazma işlemi gerçekleştirilmeden önce her zaman dosyanın sonuna geri taşınır. Bu nedenle, varolan veriler üzerine yazılamaz. **"r+"**, **"w+"** veya **"a+"** erişim türü belirtildiğinde, hem okumaya hem de yazmaya izin verilir (dosyanın güncelleştirmeye açık olduğu söylenir). Ancak, okuma ve yazma arasında geçiş yaparken, araya giren bir [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [geri sarma](rewind.md) işlemi olmalıdır. İstenirse [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) işlemi için geçerli konum belirtilebilir. Yukarıdaki değerlere ek olarak, yeni satırlar için çeviri modunu belirtmek ve dosya yönetimi için aşağıdaki karakterlerden biri *moda* eklenebilir.

|Sözleşme Dönemi|Tanım|
|----------|----------------|
|**T**|Metin (çevrilmiş) modda bir dosyayı açar. Bu modda, satır döndürme satırı beslemesi (CR-LF) kombinasyonları girişte tek satır beslemelerine (LF) ve çıktıda LF karakterlerine çevrilmiştir. Ayrıca, CTRL+Z girişte dosya sonu karakteri olarak yorumlanır. Okumak veya okumak/yazmak için açılan dosyalarda, **_fsopen** dosyanın sonunda ctrl+Z olup olmadığını kontrol eder ve mümkünse kaldırır. CtRL+Z ile biten bir dosya içinde hareket etmek için [fseek](fseek-fseeki64.md) ve [ftell'i](ftell-ftelli64.md) [kullanmak, fseek'in](fseek-fseeki64.md) dosyanın sonuna yakın uygunsuz şekilde hareket etmesinin nedeni olabilir.|
|**B**|Dosyayı ikili (çevrilmemiş) modda açar; yukarıdaki çeviriler bastırılır.|
|**S**|Önbelleğe almanın diskten sıralı erişim için en iyi duruma getirilmiş, ancak bu amaçla değil, en iyi duruma getirilmiştir.|
|**R**|Önbelleğe almanın diskten rasgele erişim için en iyi duruma getirilmiş, ancak bu amaçla kullanılmadığını belirtir.|
|**T**|Bir dosyayı geçici olarak belirtir. Mümkünse diske kızdırılmez.|
|**D**|Bir dosyayı geçici olarak belirtir. Son dosya işaretçisi kapatıldığında silinir.|

T **t** veya **b** *modunda*verilmiyorsa, çeviri modu varsayılan mod değişkeni **_fmode**ile tanımlanır. **T** veya **b** bağımsız değişkene önceden belirlenmişse, işlev başarısız olur ve **NULL**döndürür. Metin ve ikili modların tartışılması için [Metin ve İkili Mod Dosyası I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)bölümüne bakın.

Bağımsız *değişken,* Share.h'de tanımlanan aşağıdaki bildirim sabitlerinden oluşan sabit bir ifadedir.

|Sözleşme Dönemi|Tanım|
|----------|----------------|
|**_SH_COMPAT**|16 bit uygulamalar için Uyumluluk modunu ayarlar.|
|**_SH_DENYNO**|Okuma ve yazma erişimine izin verir.|
|**_SH_DENYRD**|Dosyaya erişimi okuduğunu reddediyor.|
|**_SH_DENYRW**|Dosyaya erişimi okuma ve yazmayı reddeder.|
|**_SH_DENYWR**|Dosyaya erişimi inkar ediyor.|

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgi|
|--------------|---------------------|----------------------|
|**_fsopen**|\<stdio.h>|\<share.h><br /><br /> *Shflag* parametresi için manifest sabiti için.|
|**_wfsopen**|\<stdio.h> \<veya wchar.h>|\<share.h><br /><br /> *Shflag* parametresi için manifest sabiti için.|

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
