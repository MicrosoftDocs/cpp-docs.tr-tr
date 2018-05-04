---
title: freopen, _wfreopen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
dev_langs:
- C++
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1d3c121dbe80f2eb6def9e1040b03a7b04d03689
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen

Dosya işaretçisini yeniden atar. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

## <a name="syntax"></a>Sözdizimi

```C
FILE *freopen(
   const char *path,
   const char *mode,
   FILE *stream
);
FILE *_wfreopen(
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*Yol*<br/>
Yeni dosyanın yolu.

*Modu*<br/>
İzin verilen erişim türü.

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, yeni açılan dosyasına bir işaretçi döndürür. Bir hata olursa, özgün dosya kapalı ve işlevi döndürür bir **NULL** işaretçi değeri. Varsa *yolu*, *modu*, veya *akış* null işaretçinin veya *filename* boş bir dize geçersiz bir parametre bu işlevleri çağırma bölümünde açıklandığı gibi işleyici [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **NULL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri var, bkz: [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

**Freopen** işlev ile ilişkilendirilmiş dosya kapatır *akış* ve yeniden atar *akış* tarafından belirtilen dosyaya *yolu*. **_wfreopen** bir joker karakter sürümü **_freopen**; *yolu* ve *modu* bağımsız değişkenleri **_wfreopen** olan joker karakter dizeleri. **_wfreopen** ve **_freopen** Aksi takdirde aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen** genellikle önceden açılan dosyaları yeniden yönlendirmek için kullanılan **stdin**, **stdout**, ve **stderr** kullanıcı tarafından belirtilen dosyaları. İle ilişkili yeni dosya *akış* açılmış *modu*, hangi olduğu gibi dosya için istenen erişim türünü belirten bir karakter dizesini:

|*Modu*|Access|
|-|-|
**"r"**|Okuma için açılır. Dosya yok veya bulunamadı, **freopen** çağrısı başarısız olur.
**"w"**|Boş bir dosya yazma için açılır. Verilen dosya varsa, içeriği yok.
**"a"**|Yazma (yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaret kaldırmadan ekleyerek) dosya sonunda açar. Henüz yoksa dosyası oluşturur.
**"r +"**|Hem okuma ve yazma için açılır. Dosyanın mevcut olması gerekir.
**"w +"**|Hem okumak ve yazmak için boş bir dosya açar. Dosya varsa, içeriği yok.
**"bir +"**|Okuma ve sonuna ekleme için açılır. Yeni veri dosyasına yazılmadan önce ekleme işlemi EOF işaret kaldırılmasını içerir. EOF işaret yazma tamamlandıktan sonra geri yüklenmez. Henüz yoksa dosyası oluşturur.

Kullanım **"w"** ve **"w +"** var olan dosyaları yok edebilir gibi dikkatli türleri.

Ne zaman bir dosya açıldığında ile **"a"** veya **"bir +"** erişim türüne, tüm işlemler meydana dosyanın sonunda yazma. Dosya işaretçisini kullanarak konumlandırılmasına ancak [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md), herhangi bir işlemi gerçekleştirilir yazmadan önce dosya işaretçisini her zaman geri dosyanın sonuna taşınır. Bu nedenle, varolan verilerin üzerine yazılamıyor.

**"A"** modu kaldırmaz EOF işaret dosyasına ekleyerek önce. Sonuna ekleme gerçekleştikten sonra MS-DOS türü komutu yalnızca özgün EOF işaret kadar veri ve dosyanın sonuna hiçbir veri gösterir. **"Bir +"** modunu kaldırabilirsiniz EOF işaret dosyasına ekleyerek önce. Sonuna ekleme sonra MS-DOS türü komut dosyasında tüm verileri gösterir. **"Bir +"** modu CTRL + Z EOF işaretçisi ile sonlandırılan bir akış dosyasına ekleme için gereklidir.

Zaman **"r +"**, **"w +"**, veya **"bir +"** erişim türü belirtildi, hem okuma ve yazma izin verilir (dosya "güncelleştirmesi" açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, olmalıdır bir araya giren [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [geri sarma](rewind.md) işlemi. Geçerli konum için belirtilen [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) isterseniz işlemi. Yukarıdaki değerleri ek olarak, şu karakterlerden birini eklenebilir *modu* dize yeni satırlar için çeviri modu belirtin.

|*mod* değiştiricisi|Çeviri modu|
|-|-|
**T**|Açık metin (modu çevrilmiş).
**b**|İkili (untranslated) modunda; aç satır başı ve satır besleme karakterler içeren çevirileri görüntülenmez.

Metin (çevrilmiş) modunda, satır başı satır besleme (CR-LF) birleşimleri giriş üzerinde tek yeni satır (LF) karakterleri içine çevrilir; LF karakterleri çıktıda CR LF birleşimleri için çevrilir. Ayrıca, CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. İle okuma ve yazma veya okuma için açılan dosyaları içinde **"bir +"**, çalışma zamanı kitaplığı CTRL + Z dosya sonunda olup olmadığını denetler ve, mümkünse kaldırır. Bu kullanılarak yapılır, çünkü [fseek](fseek-fseeki64.md) ve [ftell](ftell-ftelli64.md) içinde bir dosyayı taşımak için neden olabilir [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış bir şekilde davranır. **t** ANSI taşınabilirlik burada istenen kullanılmamalıdır bir Microsoft uzantısı bir seçenektir.

Varsa **t** veya **b** verilmemiştir *modu*, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [_fmode](../../c-runtime-library/fmode.md). Varsa **t** veya **b** bağımsız değişkeni, işlev başarısız olur ve döndürür önekli **NULL**.

Metin ve ikili modlarda tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**freopen**|\<stdio.h >|
|**_wfreopen**|\<stdio.h > veya \<wchar.h >|

Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_freopen.c
// compile with: /W3
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.
#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   // Reassign "stderr" to "freopen.out":
   stream = freopen( "freopen.out", "w", stderr ); // C4996
   // Note: freopen is deprecated; consider using freopen_s instead

   if( stream == NULL )
      fprintf( stdout, "error on freopen\n" );
   else
   {
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );
      fprintf( stream, "This will go to the file 'freopen.out'\n" );
      fclose( stream );
   }
   system( "type freopen.out" );
}
```

```Output
successfully reassigned
This will go to the file 'freopen.out'
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
