---
title: freopen_s, _wfreopen_s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _wfreopen_s
- freopen_s
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
- freopen_s
- _tfreopen_s
- _wfreopen_s
dev_langs:
- C++
helpviewer_keywords:
- _tfreopen_s function
- _wfreopen_s function
- file pointers [C++], reassigning
- tfreopen_s function
- wfreopen_s function
- freopen_s function
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 31840ecf42952f696dc7a51a679e54e0c53a96c9
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="freopens-wfreopens"></a>freopen_s, _wfreopen_s

Dosya işaretçisini yeniden atar. Bu sürümleri [freopen, _wfreopen](freopen-wfreopen.md) açıklandığı gibi güvenlik geliştirmeleri sahip [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t freopen(
   FILE** pFile,
   const char *path,
   const char *mode,
   FILE *stream
);
errno_t _wfreopen(
   FILE** pFile,
   const wchar_t *path,
   const wchar_t *mode,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*pFile*<br/>
Dosya işaretçisini çağrı tarafından sağlanacak bir işaretçi.

*Yol*<br/>
Yeni dosyanın yolu.

*Modu*<br/>
İzin verilen erişim türü.

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir hata kodu döndürür. Bir hata oluşursa, özgün dosya kapatıldı.

## <a name="remarks"></a>Açıklamalar

**Freopen_s** işlev ile ilişkilendirilmiş dosya kapatır *akış* ve yeniden atar *akış* tarafından belirtilen dosyaya *yolu* . **_wfreopen_s** bir joker karakter sürümü **_freopen_s**; *yolu* ve *modu* bağımsız değişkenleri **_wfreopen_s** olan joker karakter dizeleri. **_wfreopen_s** ve **_freopen_s** Aksi takdirde aynı şekilde davranır.

Varsa *pFile*, *yolu*, *modu*, veya *akış* olan **NULL**, veya *yolu* boş bir dize açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve geri dönüp **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen_s**|**freopen_s**|**freopen_s**|**_wfreopen_s**|

**freopen_s** genellikle önceden açılan dosyaları yeniden yönlendirmek için kullanılan **stdin**, **stdout**, ve **stderr** kullanıcı tarafından belirtilen dosyaları. İle ilişkili yeni dosya *akış* açılmış *modu*, hangi olduğu gibi dosya için istenen erişim türünü belirten bir karakter dizesini:

|*Modu*|Access|
|-|-|
**"r"**|Okuma için açılır. Dosya yok veya bulunamadı, **freopen_s** çağrısı başarısız olur.
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
|**freopen_s**|\<stdio.h >|
|**_wfreopen_s**|\<stdio.h > veya \<wchar.h >|

Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_freopen_s.c
// This program reassigns stderr to the file
// named FREOPEN.OUT and writes a line to that file.

#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   errno_t err;
   // Reassign "stderr" to "freopen.out":
   err = freopen_s( &stream, "freopen.out", "w", stderr );

   if( err != 0 )
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
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
