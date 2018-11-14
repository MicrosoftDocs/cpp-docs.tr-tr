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
ms.openlocfilehash: 2cdc16f21882c32933868000c6fd1d66accc74b8
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326518"
---
# <a name="freopens-wfreopens"></a>freopen_s, _wfreopen_s

Dosya işaretçisini yeniden atar. Bu sürümleri [freopen, _wfreopen](freopen-wfreopen.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Çağrı tarafından sağlanacak dosya işaretçisini bir işaretçi.

*Yolu*<br/>
Yeni dosyanın yolu.

*Modu*<br/>
İzin verilen erişim türü.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, bir hata kodu döndürür. Bir hata oluşursa, özgün dosya kapatılır.

## <a name="remarks"></a>Açıklamalar

**Freopen_s** işlevi şu anda ilişkili dosyayı kapatır *stream* ve yeniden atar *stream* tarafından belirtilen dosyaya *yolu* . **_wfreopen_s** geniş karakterli sürümüdür **_freopen_s**; *yolu* ve *modu* bağımsız değişkenleri **_wfreopen_s** olan geniş karakterli dizelerdir. **_wfreopen_s** ve **_freopen_s** aynı şekilde davranır.

Varsa *pFile*, *yolu*, *modu*, veya *stream* olan **NULL**, veya *yolu* boş bir dize ise bu işlevler içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen_s**|**freopen_s**|**freopen_s**|**_wfreopen_s**|

**freopen_s** genellikle önceden açılmış dosyalar yeniden yönlendirmek için kullanılan **stdin**, **stdout**, ve **stderr** kullanıcı tarafından belirtilen dosya için. İle ilişkili yeni dosya *stream* açılmış *modu*, olduğu gibi dosya için istenen erişim türünü belirten bir karakter dizesi:

|*Modu*|Access|
|-|-|
| **"r"** | Okuma için açar. Dosya mevcut değil ya da bulunamıyorsa **freopen_s** çağrısı başarısız olur. |
| **"w"** | Yazma için boş bir dosya açar. Verilen dosya varsa içeriği yok edilir. |
| **"a"** | (Ekleme dosyaya yeni veri yazılmadan önce dosya sonu (EOF) işaretçisini kaldırmadan) dosyanın sonunda yazma için açar. Henüz yoksa dosyayı oluşturur. |
| **"r +"** | Hem okuma ve yazma için açar. Dosyanın mevcut olması gerekir. |
| **"w +"** | Hem okuma ve yazma için boş bir dosya açar. Dosya varsa içeriği yok edilir. |
| **"a +"** | Okuma ve ekleme için açar. Ekleme işlemi, dosyaya yeni veri yazılmadan önce EOF işaretinin kaldırılmasını içerir. Yazma tamamlandıktan sonra EOF işaretçisi geri yüklenmez. Henüz yoksa dosyayı oluşturur. |

Kullanım **"w"** ve **"w +"** türleri dikkatli olarak var olan dosyaları yok edebilir.

Ne zaman bir dosya açıldığında ile **"a"** veya **"a +"** erişim türü, tüm yazma işlemlerini gerçekleştiğinde dosyanın sonunda. Dosya işaretçisi kullanılarak konumlandırılabilir rağmen [fseek](fseek-fseeki64.md) veya [rewind](rewind.md), herhangi bir işlemi yazma önce dosya işaretçisini her zaman geri dosyanın sonuna kadar taşınır. Bu nedenle, var olan verilerin üzerine yazılamaz.

**"A"** modu kaldırmaz EOF işaretçisi önce dosyasına ekleme. Ekleme oluştuktan sonra MS-DOS TYPE komutu özgün EOF işaretçisi verileri ve dosyaya eklenen herhangi bir veriyi değil yalnızca gösterir. **"A +"** modu EOF işaret metnini kaldırır önce dosyasına ekleme. Ekleme işleminde sonra MS-DOS TYPE komutu dosyasında tüm verileri gösterir. **"A +"** modu CTRL + Z EOF işaretiyle biten bir akış dosyasına ekleme için gereklidir.

Zaman **"r +"**, **"w +"**, veya **"a +"** erişim türü belirtildiğinde, hem okumaya hem yazmaya izin verilir (dosyanın "güncelleştirme" açık olarak kabul edilir). Ancak, yazma ve okuma arasında geçiş yaptığınızda, olmalıdır bir araya giren [fsetpos](fsetpos.md), [fseek](fseek-fseeki64.md), veya [rewind](rewind.md) işlemi. Geçerli konum için belirtilen [fsetpos](fsetpos.md) veya [fseek](fseek-fseeki64.md) isterseniz işlemi. Yukarıdaki değerlerden ek olarak, şu karakterlerden birini eklenebilir *modu* dizesini yeni satırlar için çeviri modunu belirtin.

|*modu* değiştiricisi|Çeviri modu|
|-|-|
| **T** | Açık metin (çevrilmiş) modunda. |
| **b** | İkili (çevrilmemiş) modda; açık satır başı ve satır besleme karakterlerini içeren Çeviriler bastırılır. |

Metin (çevrilmiş) modunda, satır başı satır besleme (CR-LF) kombinasyonları girişte tek satır başı Besleme (LF) karakterleri çevrilir; LF karakterleri için çıkış CR-LF kombinasyonlarına çevrilir. Ayrıca, CTRL + Z girişteki bir dosya sonu karakteri olarak yorumlanır. İle okuma ve yazma için okuma veya açık dosyalardaki **"a +"**, çalışma zamanı kitaplığı, CTRL + Z dosya sonunda olup olmadığını denetler ve eğer mümkünse bunu kaldırır. Kullanıldığından yapıldığını [fseek](fseek-fseeki64.md) ve [ftell](ftell-ftelli64.md) neden olabilir bir dosya içinde hareket etmek [fseek](fseek-fseeki64.md) dosyanın sonuna yakın yanlış davranmasına. **t** ANSI taşınabilirliğinin istendiği durumlarda kullanılmamalıdır bir Microsoft uzantısı bir seçenektir.

Varsa **t** veya **b** verilmez *modu*, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [_fmode](../../c-runtime-library/fmode.md). Varsa **t** veya **b** bağımsız değişken, işlev başarısız olur ve döndürür önekli **NULL**.

Metin ve ikili modlarının bir tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**freopen_s**|\<stdio.h >|
|**_wfreopen_s**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
