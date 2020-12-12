---
description: 'Hakkında daha fazla bilgi edinin: _fsopen _wfsopen'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c7b54a6735939e26c8ff0153abc640e3dc2c8b41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318344"
---
# <a name="_fsopen-_wfsopen"></a>_fsopen, _wfsopen

Dosya paylaşımı olan bir akış açar.

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

*modundaysa*<br/>
İzin verilen erişim türü.

*shflag*<br/>
İzin verilen paylaşım türü.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri akışa bir işaretçi döndürür. Null işaretçi değeri bir hatayı gösterir. *Dosya adı* veya *mod* **null** ya da boş bir dize ise, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **null** döndürür ve **errno** , **EINVAL** olarak ayarlanır.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Fsopen** işlevi dosya *adı* tarafından belirtilen dosyayı bir akış olarak açar ve mod ve *shflag* bağımsız değişkenleri tarafından tanımlanan şekilde dosyayı sonraki paylaşılan okuma veya yazma için hazırlar. **_wfsopen** , **_fsopen** geniş karakterli bir sürümüdür; _wfsopen *dosya adı* ve *mod* bağımsız  değişkenleri geniş karakterli dizelerdir. **_wfsopen** ve **_fsopen** aynı şekilde davranır.

Karakter dizesi *modu* , aşağıdaki tabloda gösterildiği gibi, dosya için istenen erişim türünü belirtir.

|Süre|Tanım|
|----------|----------------|
|**sağ**|Okuma için açılır. Dosya yoksa veya bulunamıyorsa, **_fsopen** çağrısı başarısız olur.|
|**anlatımı**|Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir.|
|**a**|Dosyanın sonuna yazmak için açılır (ekleme); Dosya yoksa, önce dosyayı oluşturur.|
|**"r +"**|Hem okuma hem de yazma için açılır. (Dosyanın mevcut olması gerekir.)|
|**"w +"**|Hem okuma hem de yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir.|
|**"a +"**|Okuma ve ekleme için açılır; Dosya yoksa, önce dosyayı oluşturur.|

Mevcut dosyaları yok etmek için **"w"** ve **"w +"** türlerini dikkatli kullanın.

**"A"** veya **"a +"** erişim türüyle bir dosya açıldığında, dosyanın sonunda tüm yazma işlemleri gerçekleşir. Dosya işaretçisi, [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilir, ancak herhangi bir yazma işlemi yapılmadan önce her zaman dosyanın sonuna geri taşınır. Bu nedenle, mevcut verilerin üzerine yazılamaz. **"R +"**, **"w +"** veya **"a +"** erişim türü belirtildiğinde, hem okuma hem de yazma için izin verilir (dosyanın güncelleştirme için açık olduğu söylenir). Ancak, okuma ve yazma arasında geçiş yaparken, aradaki bir [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md)veya [geri sarma](rewind.md) işlemi olmalıdır. İsterseniz, [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) işlemi için geçerli konum belirtilebilir. Yukarıdaki değerlere ek olarak, yeni satırlar için çeviri modunu belirtmek ve dosya yönetimi için aşağıdaki karakterlerden biri *moda* dahil edilebilir.

|Süre|Tanım|
|----------|----------------|
|**şı**|Metin (çevrilmiş) modunda bir dosya açar. Bu modda, satır başı satır besleme (CR-LF) birleşimleri, giriş ve LF karakterleri üzerinde tek satırlık akışlara (LF) çevrilir ve çıkışta CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. Okuma veya okuma/yazma için açılan dosyalarda, **_fsopen** DOSYANıN sonunda CTRL + Z olup olmadığını denetler ve mümkünse onu kaldırır. Bu işlem yapılır çünkü bu, CTRL + Z ile biten bir dosya içinde gezinmek için [fseek](fseek-fseeki64.md) ve [fsöyleyin](ftell-ftelli64.md) kullanılması, [fseek](fseek-fseeki64.md) 'in dosyanın sonuna doğru şekilde davranmasına neden olabilir.|
|**kenarı**|İkili (çevrilmemiş) modda bir dosya açar; Yukarıdaki Çeviriler bastırılır.|
|**S**|Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere önbelleğe alınan bir disk erişimi belirtir.|
|**R**|Önbellek için en iyi duruma getirilmiş, ancak sınırlı olmamak üzere, diskten rastgele erişim|
|**T**|Geçici olarak bir dosya belirtir. Mümkünse, diske boşaltılmaz.|
|**TID**|Geçici olarak bir dosya belirtir. Son dosya işaretçisi kapatıldığında silinir.|

**T** veya **b** *modda* verilmezse, çeviri modu **_fmode** varsayılan mod değişkeni tarafından tanımlanır. **T** veya **b** bağımsız değişkene öneki varsa, Işlev başarısız olur ve **null** değerini döndürür. Metin ve ikili modların bir tartışması için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

*Shflag* bağımsız değişkeni, Share. h içinde tanımlanan aşağıdaki bildirim sabitlerinden birini içeren sabit bir ifadedir.

|Süre|Tanım|
|----------|----------------|
|**_SH_COMPAT**|16 bit uygulamalar için uyumluluk modunu ayarlar.|
|**_SH_DENYNO**|Okuma ve yazma erişimine izin verir.|
|**_SH_DENYRD**|Dosyaya okuma erişimini engeller.|
|**_SH_DENYRW**|Dosyaya okuma ve yazma erişimini reddeder.|
|**_SH_DENYWR**|Dosyaya yazma erişimini reddeder.|

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfsopen**|**_fsopen**|**_fsopen**|**_wfsopen**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|İsteğe bağlı üstbilgiler|
|--------------|---------------------|----------------------|
|**_fsopen**|\<stdio.h>|\<share.h><br /><br /> *Shflag* parametresi için bildirim sabiti.|
|**_wfsopen**|\<stdio.h> veya \<wchar.h>|\<share.h><br /><br /> *Shflag* parametresi için bildirim sabiti.|

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[ferror](ferror.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
[_sopen, _wsopen](sopen-wsopen.md)<br/>
