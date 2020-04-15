---
title: freopen_s, _wfreopen_s
ms.date: 4/2/2020
api_name:
- _wfreopen_s
- freopen_s
- _o__wfreopen_s
- _o_freopen_s
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
- freopen_s
- _tfreopen_s
- _wfreopen_s
helpviewer_keywords:
- _tfreopen_s function
- _wfreopen_s function
- file pointers [C++], reassigning
- tfreopen_s function
- wfreopen_s function
- freopen_s function
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
ms.openlocfilehash: a24e34ead905d2f704bfbf4d829064c656272e97
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345911"
---
# <a name="freopen_s-_wfreopen_s"></a>freopen_s, _wfreopen_s

Bir dosya işaretçisini yeniden atar. [Fret'teki](freopen-wfreopen.md) Güvenlik Özellikleri'nde açıklandığı gibi, _wfreopen bu [sürümlerinde](../../c-runtime-library/security-features-in-the-crt.md)güvenlik geliştirmeleri vardır.

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
Arama tarafından sağlanacak dosya işaretçisine bir işaretçi.

*Yolu*<br/>
Yeni dosyayolu.

*Modu*<br/>
Erişim türüne izin verilir.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir hata kodu döndürür. Bir hata oluşursa, özgün dosya kapatılır.

## <a name="remarks"></a>Açıklamalar

**freopen_s** işlevi şu anda *akışla* ilişkili dosyayı kapatır ve *yol*tarafından belirtilen dosyaya *akışı* yeniden atar. **_wfreopen_s** **_freopen_s**geniş karakterli bir versiyonudur; *_wfreopen_s yol* ve *mod* bağımsız değişkenleri geniş karakterli dizeleridir. **_wfreopen_s** **_wfreopen_s** ve **_freopen_s** aynı şekilde davranan.

*PFile,* *path,* *mode*veya *stream* herhangi biri **NULL**ise veya *yol* boş bir dize ise, bu işlevler [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütme devam etmesine izin verilirse, bu işlevler EINVAL **için errno** ayarlayın ve **EINVAL** döndürün. **EINVAL**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen_s**|**freopen_s**|**freopen_s**|**_wfreopen_s**|

**freopen_s** genellikle önceden açılmış dosyaları **stdin,** **stdout**ve **stderr** kullanıcı tarafından belirtilen dosyalara yönlendirmek için kullanılır. *Akışla* ilişkili yeni dosya, dosya için istenen erişim türünü belirten bir karakter dizesi olan *modla*açılır:

|*Modu*|Erişim|
|-|-|
| **"r"** | Okumak için açılır. Dosya yoksa veya bulunamıyorsa, **freopen_s** aramabaşarısız olur. |
| **"w"** | Yazmak için boş bir dosya yı açar. Verilen dosya varsa, içeriği yok edilir. |
| **"a"** | Dosyaya yeni veriler yazılmadan önce dosya sonu (EOF) işaretçisini kaldırmadan dosyanın sonunda (ek) yazıiçin açılır. Yoksa dosyayı oluşturur. |
| **"r+"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w+"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a+"** | Okuma ve ekolarak açılır. Ek işlem, dosyaya yeni veriler yazılmadan önce EOF işaretçisinin kaldırılmasını içerir. EOF işaretçisi, yazma tamamlandıktan sonra geri yüklenmez. Yoksa dosyayı oluşturur. |

Varolan dosyaları yok edebileceğinden, **"w"** ve **"w+"** türlerini dikkatli kullanın.

Bir dosya **"a" veya "a+"** erişim türüyle açıldığında, tüm yazma işlemleri dosyanın sonunda gerçekleşir. **"a+"** Dosya işaretçisi [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilse de, dosya işaretçisi herhangi bir yazma işlemi gerçekleştirilmeden önce her zaman dosyanın sonuna geri taşınır. Bu nedenle, varolan veriler üzerine yazılamaz.

**"a"** modu, dosyaya ekilmeden önce EOF işaretçisini kaldırmaz. Ek olay dan sonra, MS-DOS TYPE komutu yalnızca özgün EOF işaretçisine kadar olan verileri gösterir ve dosyaya eklenen verileri göstermez. **"a+"** modu, dosyaya ekilmeden önce EOF işaretçisini kaldırır. Ekledikten sonra, MS-DOS TYPE komutu dosyadaki tüm verileri gösterir. CTRL+Z EOF işaretçisi ile sonlandırılan bir akış dosyasına ekolarak **"a+"** modu gereklidir.

**"r+"**, **"w+"** veya **"a+"** erişim türü belirtildiğinde, hem okumaya hem de yazmaya izin verilir (dosyanın "güncelleştirme" için açık olduğu söylenir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, araya giren bir [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [geri sarma](rewind.md) işlemi olmalıdır. İstenirse [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) işlemi için geçerli konum belirtilebilir. Yukarıdaki değerlere ek olarak, yeni satırlar için çeviri modunu belirtmek için aşağıdaki karakterlerden biri *mod* dizesine eklenebilir.

|*mod* değiştirici|Çeviri modu|
|-|-|
| **T** | Metin (çevrilmiş) modunda açın. |
| **B** | İkili (çevrilmemiş) modda açık; satır döndürme ve satır besleme karakterlerini içeren çeviriler bastırılır. |

Metin (çevrilmiş) modda, satır satır besleme (CR-LF) kombinasyonları girişte tek satır besleme (LF) karakterlere çevrilir; LF karakterleri çıktıdaki CR-LF kombinasyonlarına çevrilir. Ayrıca, CTRL+Z girişte dosya sonu karakteri olarak yorumlanır. Okumak veya **"a+"** ile yazmak ve okumak için açılan dosyalarda, çalışma zamanı kitaplığı dosyanın sonundactrl+Z olup olmadığını denetler ve mümkünse kaldırır. Bu, bir dosya içinde taşımak için [fseek](fseek-fseeki64.md) ve [ftell](ftell-ftelli64.md) kullanarak [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış hareket neden olabilir, çünkü yapılır. **t** seçeneği, ANSI taşınabilirliğinin istendiği durumlarda kullanılmaması gereken bir Microsoft uzantısıdır.

**T** veya **b** *modunda*verilmiyorsa, varsayılan çeviri modu _fmode genel [değişken](../../c-runtime-library/fmode.md)tarafından tanımlanır. **T** veya **b** bağımsız değişkene önceden belirlenmişse, işlev başarısız olur ve **NULL**döndürür.

Metin ve ikili modların tartışılması için [Metin ve İkili Mod Dosyası I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)bölümüne bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**freopen_s**|\<stdio.h>|
|**_wfreopen_s**|\<stdio.h> \<veya wchar.h>|

Konsol, Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Konsol, **stdin,** **stdout**ve **stderr**ile ilişkili standart akış kolları, C çalışma zamanı işlevleri UWP uygulamalarında bunları kullanamadan önce yönlendirilmelidir. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
