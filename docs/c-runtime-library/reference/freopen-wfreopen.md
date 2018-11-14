---
title: freopen, _wfreopen
ms.date: 11/04/2016
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
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
ms.openlocfilehash: 4c570837bddea1f5e986ae5f767279ab2637ea21
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332510"
---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen

Dosya işaretçisini yeniden atar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

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

*Yolu*<br/>
Yeni dosyanın yolu.

*Modu*<br/>
İzin verilen erişim türü.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, yeni açık dosyaya bir işaretçi döndürür. Bir hata meydana gelir, özgün dosya kapatılır ve işlev döndürür bir **NULL** işaretçi değeri. Varsa *yolu*, *modu*, veya *stream* null bir işaretçiyse veya *filename* boş bir dize ise bu işlevler geçersiz parametre çağırma bölümünde anlatıldığı gibi işleyici [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **NULL**.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin daha güvenli sürümleri mevcut, bkz: [freopen_s, _wfreopen_s](freopen-s-wfreopen-s.md).

**Freopen** işlevi şu anda ilişkili dosyayı kapatır *stream* ve yeniden atar *stream* tarafından belirtilen dosyaya *yolu*. **_wfreopen** geniş karakterli sürümüdür **_freopen**; *yolu* ve *modu* bağımsız değişkenleri **_wfreopen** olan geniş karakterli dizelerdir. **_wfreopen** ve **_freopen** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tfreopen**|**freopen**|**freopen**|**_wfreopen**|

**freopen** genellikle önceden açılmış dosyalar yeniden yönlendirmek için kullanılan **stdin**, **stdout**, ve **stderr** kullanıcı tarafından belirtilen dosya için. İle ilişkili yeni dosya *stream* açılmış *modu*, olduğu gibi dosya için istenen erişim türünü belirten bir karakter dizesi:

|*Modu*|Access|
|-|-|
| **"r"** | Okuma için açar. Dosya mevcut değil ya da bulunamıyorsa **freopen** çağrısı başarısız olur. |
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
|**freopen**|\<stdio.h >|
|**_wfreopen**|\<stdio.h > veya \<wchar.h >|

Konsolu, Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsolları ile ilişkili standart akış işleyicileri **stdin**, **stdout**, ve **stderr**, C çalışma zamanı işlevleri bunları UWP uygulamalarında kullanmadan önce yeniden yönlendirilmesi gerekiyor . Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[_fileno](fileno.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmode](setmode.md)<br/>
