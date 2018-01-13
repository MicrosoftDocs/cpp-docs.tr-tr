---
title: freopen, _wfreopen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d3eb18b70ea672b095dc6d24dfd45e1bdda8f88b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen
Dosya işaretçisini yeniden atar. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [freopen_s, _wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
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
  
#### <a name="parameters"></a>Parametreler  
 `path`  
 Yeni dosyanın yolu.  
  
 `mode`  
 İzin verilen erişim türü.  
  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri, yeni açılan dosyasına bir işaretçi döndürür. Bir hata oluştuğunda özgün dosya kapatılır ve işlevi döndürür bir `NULL` işaretçi değeri. Varsa `path`, `mode`, veya `stream` null işaretçinin veya `filename` boş bir dize açıklandığı gibi bu işlevleri geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EINVAL` ve geri dönüp `NULL`.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin daha güvenli sürümleri var, bkz: [freopen_s, _wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
 `freopen` İşlev ile ilişkilendirilmiş dosya kapatır `stream` ve yeniden atar `stream` tarafından belirtilen dosyaya `path`. `_wfreopen`bir joker karakter sürümü `_freopen`; `path` ve `mode` bağımsız değişkenleri `_wfreopen` joker karakter dizelerdir. `_wfreopen`ve `_freopen` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfreopen`|`freopen`|`freopen`|`_wfreopen`|  
  
 `freopen`genellikle önceden açılan dosyaları yeniden yönlendirmek için kullanılan `stdin`, `stdout`, ve `stderr` kullanıcı tarafından belirtilen dosyaları. İle ilişkili yeni dosya `stream` açılmış `mode`, hangi olduğu gibi dosya için istenen erişim türünü belirten bir karakter dizesini:  
  
 `"r"`  
 Okuma için açılır. Dosya yok veya bulunamadı, `freopen` çağrısı başarısız olur.  
  
 `"w"`  
 Boş bir dosya yazma için açılır. Verilen dosya varsa, içeriği yok.  
  
 `"a"`  
 Yazma (yeni veriler; dosyasına yazılırken önce EOF işaret kaldırmadan ekleyerek) dosya sonunda açar henüz yoksa dosyayı ilk olarak oluşturur.  
  
 `"r+"`  
 Hem okuma ve yazma için açılır. (Dosya var olmalıdır.)  
  
 `"w+"`  
 Hem okumak ve yazmak için boş bir dosya açar. Verilen dosya varsa, içeriği yok.  
  
 `"a+"`  
 Okuma ve sonuna ekleme açar; ekleme işlemi, yeni veri dosyasına yazılır ve EOF işaret yazma tamamlandıktan sonra geri önce EOF işaret kaldırılmasını içerir; henüz yoksa dosyayı ilk olarak oluşturur.  
  
 Kullanım `"w"` ve `"w+"` var olan dosyaları yok edebilir gibi dikkatli türleri.  
  
 Ne zaman bir dosya açıldığında ile `"a"` veya `"a+"` erişim türüne, tüm işlemler meydana dosyanın sonunda yazma. Dosya işaretçisini kullanarak konumlandırılmasına ancak `fseek` veya `rewind`, herhangi bir işlemi gerçekleştirilir yazmadan önce dosya işaretçisini her zaman geri dosyanın sonuna taşınır. Bu nedenle, varolan verilerin üzerine yazılamıyor.  
  
 `"a"` Modu kaldırmaz EOF işaret dosyasına ekleyerek önce. Sonuna ekleme gerçekleştikten sonra MS-DOS türü komutu yalnızca özgün EOF işaret kadar veri ve dosyanın sonuna hiçbir veri gösterir. `"a+"` Modunu kaldırabilirsiniz EOF işaret dosyasına ekleyerek önce. Sonuna ekleme sonra MS-DOS türü komut dosyasında tüm verileri gösterir. `"a+"` Modu CTRL + Z EOF işaretçisi ile sonlandırılan bir akış dosyasına ekleme için gereklidir.  
  
 Zaman `"r+"`, `"w+"`, veya `"a+"` erişim türü belirtildi, hem okuma ve yazma izin verilir (dosya "güncelleştirmesi" açık olarak kabul edilir). Ancak, okuma ve yazma arasında geçiş yaptığınızda, olmalıdır bir araya giren [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md), veya [geri sarma](../../c-runtime-library/reference/rewind.md) işlemi. Geçerli konum için belirtilen `fsetpos` veya `fseek` isterseniz işlemi. Yukarıdaki değerleri ek olarak, şu karakterlerden birini eklenebilir `mode` dize yeni satırlar için çeviri modu belirtin.  
  
 `t`  
 Açık metin (modu çevrilen); satır başı satır besleme (CR-LF) birleşimleri giriş üzerinde tek yeni satır (LF) karakterleri içine dönüştürülür; LF karakterleri çıktıda CR LF birleşimleri için çevrilir. Ayrıca, CTRL + Z giriş üzerinde bir dosya sonu karakteri olarak yorumlanır. İle okuma ve yazma veya okuma için açılan dosyaları içinde `"a+"`, çalışma zamanı kitaplığı CTRL + Z dosya sonunda olup olmadığını denetler ve, mümkünse kaldırır. Bu kullanılarak yapılır, çünkü `fseek` ve `ftell` içinde bir dosyayı taşımak için neden olabilir `fseek` dosyanın sonuna yakın yanlış bir şekilde davranır. `t` ANSI taşınabilirlik burada istenen kullanılmamalıdır bir Microsoft uzantısı bir seçenektir.  
  
 `b`  
 İkili (untranslated) modunda; aç Yukarıdaki çevirileri görüntülenmez.  
  
 Varsa `t` veya `b` verilmemiştir `mode`, varsayılan çeviri modu genel değişkeni tarafından tanımlanan [_fmode](../../c-runtime-library/fmode.md). Varsa `t` veya `b` bağımsız değişkeni, işlev başarısız olur ve döndürür önekli `NULL`.  
  
 Metin ve ikili modlarda tartışma için bkz [metin ve ikili mod dosyası g/ç](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`freopen`|\<stdio.h >|  
|`_wfreopen`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol desteklenmeyen [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)