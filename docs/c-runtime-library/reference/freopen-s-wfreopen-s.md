---
title: freopen_s, _wfreopen_s
ms.date: 11/04/2016
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
helpviewer_keywords:
- _tfreopen_s function
- _wfreopen_s function
- file pointers [C++], reassigning
- tfreopen_s function
- wfreopen_s function
- freopen_s function
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
ms.openlocfilehash: 6efe858713bf8c315536098f1b6dabdbcba01bfa
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376118"
---
# <a name="freopens-wfreopens"></a>freopen_s, _wfreopen_s

Bir dosya işaretçisini yeniden atar. [Serbest açık, _wfreopen](freopen-wfreopen.md) 'un bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

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
Çağrı tarafından sağlanacak dosya işaretçisine yönelik bir işaretçi.

*Yolu*<br/>
Yeni dosyanın yolu.

*modundaysa*<br/>
İzin verilen erişim türü.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir hata kodu döndürür. Bir hata oluşursa, özgün dosya kapatılır.

## <a name="remarks"></a>Açıklamalar

**Freopen_s** işlevi, *Stream* ile ilişkili olan dosyayı kapatır ve Stream tarafından belirtilen dosyaya yeniden atama *akışı* *atar.* **_wfreopen_s** , **_freopen_s**öğesinin geniş karakterli bir sürümüdür; **_wfreopen_s** için *yol* ve *mod* bağımsız değişkenleri geniş karakterli dizelerdir. **_wfreopen_s** ve **_freopen_s** aynı şekilde davranır.

*Pfıle*, *Path*, *Mode*veya *Stream* herhangi biri **null**Ise veya *yol* boş bir dize ise, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **EINVAL**döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen_s**|**freopen_s**|**freopen_s**|**_wfreopen_s**|

**freopen_s** , genellikle, önceden açılan dosyaları **stdin**, **stdout**ve **stderr** 'i Kullanıcı tarafından belirtilen dosyalara yönlendirmek için kullanılır. *Stream* ile ilişkili yeni dosya, dosya için istenen erişimin türünü belirten, aşağıdaki gibi bir karakter dizesi olan *moduyla*açılır:

|*modundaysa*|Access|
|-|-|
| **"r"** | Okuma için açılır. Dosya yoksa veya bulunamazsa, **freopen_s** çağrısı başarısız olur. |
| **"w"** | Yazma için boş bir dosya açar. Verilen dosya varsa, içeriği yok edilir. |
| **a** | Dosyanın sonuna (ekleme), yeni veriler dosyaya yazılmadan önce dosya sonu (EOF) işaretini kaldırmadan açılır. Yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma hem de yazma için açılır. Dosya var olmalıdır. |
| **"w +"** | Hem okuma hem de yazma için boş bir dosya açar. Dosya varsa, içeriği yok edilir. |
| **"a +"** | Okuma ve ekleme için açılır. Ekleme işlemi, yeni veriler dosyaya yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma işlemi tamamlandıktan sonra EOF işaretleyicisi geri yüklenmez. Yoksa dosyayı oluşturur. |

Mevcut dosyaları yok etmek için **"w"** ve **"w +"** türlerini dikkatli kullanın.

Bir dosya, **"a"** veya **"a +"** erişim türüyle açıldığında, dosyanın sonunda tüm yazma işlemleri gerçekleşir. Dosya işaretçisi [fseek](fseek-fseeki64.md) veya [geri sarma](rewind.md)kullanılarak yeniden konumlandırılabilse de, herhangi bir yazma işlemi yapılmadan önce dosya işaretçisi her zaman dosyanın sonuna taşınır. Bu nedenle, mevcut verilerin üzerine yazılamaz.

**"A"** modu, dosyaya ekleme yapmadan önce EOF işaretçisini kaldırmaz. Ekleme gerçekleştirildikten sonra, MS-DOS türü komutu yalnızca özgün EOF işaretine kadar olan verileri gösterir ve dosyaya eklenen verileri etkilemez. **"A +"** modu, dosyaya ekleme yapmadan önce EOF işaretçisini kaldırır. Eklendikten sonra, MS-DOS türü komutu dosyadaki tüm verileri gösterir. **"A +"** modu, CTRL + Z EOF işaretleyicisi ile sonlandırılan bir akış dosyasına ekleme için gereklidir.

**"R +"** , **"w +"** ya da **"a +"** erişim türü belirtildiğinde, hem okuma hem de yazma için izin verilir (dosya "güncelleştirme" için açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, aradaki bir [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md)veya [geri sarma](rewind.md) işlemi olmalıdır. İsterseniz, [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) işlemi için geçerli konum belirtilebilir. Yukarıdaki değerlere ek olarak, yeni satırlar için çeviri modunu belirtmek üzere *mod* dizesine aşağıdaki karakterlerden biri dahil edilebilir.

|*mod* değiştiricisi|Çeviri modu|
|-|-|
| **şı** | Metin (çevrilmiş) modunda aç. |
| **b** | İkili (çevrilmemiş) modda aç; satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin (çevrilmiş) modunda, satır başı satır besleme (CR-LF) birleşimleri, girişte tek satırlık akış (LF) karakterlerine çevrilir; LF karakterleri çıkışındaki CR-LF birleşimlerine çevrilir. Ayrıca CTRL + Z, girişte bir dosya sonu karakteri olarak yorumlanır. **"A +"** ile yazma ve okuma için açılan dosyalarda, çalışma zamanı kitaplığı dosyanın sonunda bir CTRL + Z 'yi denetler ve mümkünse onu kaldırır. Bu, bir dosya içinde geçiş yapmak için [fseek](fseek-fseeki64.md) ve [fsöyleyin](ftell-ftelli64.md) kullanmanın, [fseek](fseek-fseeki64.md) dosyasının sonuna doğru şekilde davranmasına neden olabileceği için yapılır. **T** SEÇENEĞI, ANSI taşınabilirliği istendiği yerde kullanılması gereken bir Microsoft uzantısıdır.

**T** veya **b** *modunda*verilmezse, varsayılan çeviri modu, [_fmode](../../c-runtime-library/fmode.md)genel değişkeni tarafından tanımlanır. **T** veya **b** bağımsız değişkene öneki varsa, Işlev başarısız olur ve **null**değerini döndürür.

Metin ve ikili modların bir tartışması için bkz. [metin ve Ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**freopen_s**|\<stdio. h >|
|**_wfreopen_s**|\<stdio. h > veya \<wchar. h >|

Konsol Evrensel Windows Platformu (UWP) uygulamalarında desteklenmez. Console, **STDIN**, **stdout**ve **stderr**Ile ilişkili standart akış TUTAMAÇLARı, C çalışma zamanı işlevlerinin UWP uygulamalarında kullanabilmesi için yeniden yönlendirilmelidir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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
