---
title: "Akış t-O | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- I/O routines, stream I/O
- I/O [CRT], stream
- stream I/O
ms.assetid: dc7874d3-a91b-456a-9015-4748bb358217
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6a0c3fe1a85028f4b4220f8e2f111afa1012121
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="stream-io"></a>Akış G/Ç
Bu işlevler farklı boyutlarda ve büyük veri yapılarına tek karakter biçimlerinden verilerini işler. Ayrıca arabelleğe alma, performansı artırmak sağlarlar. Akış Arabellek varsayılan boyutu 4 K'dır. Bu yordamlar, yalnızca çalışma zamanı kitaplığı yordamları tarafından oluşturulan arabellekleri etkiler ve işletim sistemi tarafından oluşturulan arabellekleri üzerinde hiçbir etkisi yoktur.  
  
### <a name="stream-io-routines"></a>Akış g/ç yordamları  
  
|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|  
|-------------|---------|  
|[clearerr](../c-runtime-library/reference/clearerr.md), [clearerr_s](../c-runtime-library/reference/clearerr-s.md)|Akış için NET hata göstergesi|  
|[fclose](../c-runtime-library/reference/fclose-fcloseall.md)|Kapat akış|  
|[_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)|Açık olan tüm akışlar dışında kapatmak `stdin`, `stdout`, ve`stderr`|  
|[_fdopen, wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Akış açık dosyanın dosya tanımlayıcısı ile ilişkilendirme|  
|[feof](../c-runtime-library/reference/feof.md)|Dosya sonu akış üzerinde sınayın|  
|[ferror](../c-runtime-library/reference/ferror.md)|Akış hatası sınayın|  
|[fflush](../c-runtime-library/reference/fflush.md)|Akışı arabelleğe veya depolama aygıtına temizleme|  
|[fgetc, fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md)|Karakter akışından okuma (işlev sürümlerini `getc` ve `getwc`)|  
|[_fgetchar, _fgetwchar](../c-runtime-library/reference/fgetc-fgetwc.md)|Karakter okuma `stdin` (işlev sürümlerini `getchar` ve `getwchar`)|  
|[fgetpos](../c-runtime-library/reference/fgetpos.md)|Akışın konumu göstergesi Al|  
|[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)|Dize akışından okuma|  
|[_fileno](../c-runtime-library/reference/fileno.md)|Akışı ile ilişkilendirilmiş dosya tanımlayıcısı Al|  
|[_flushall](../c-runtime-library/reference/flushall.md)|Arabellek veya depolama aygıtı için tüm akışları temizleme|  
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Açık akış|  
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|Biçimlendirilmiş verileri akışına yazma|  
|[fputc, fputwc](../c-runtime-library/reference/fputc-fputwc.md)|Bir karakterin bir akışa yazma (işlev sürümlerini `putc` ve `putwc`)|  
|[_fputchar, _fputwchar](../c-runtime-library/reference/fputc-fputwc.md)|Karakter yazma `stdout` (işlev sürümlerini `putchar` ve `putwchar`)|  
|[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)|Dize akışına yazma|  
|[fread](../c-runtime-library/reference/fread.md)|Biçimlendirilmemiş veri akışından okuma|  
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Yeniden atama `FILE` yeni dosya veya aygıt akış işaretçi|  
|[fscanf, fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|Veri akışından okuma biçimlendirilmiş|  
|[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)|Taşıma dosya konumuna konumu verilen|  
|[fsetpos](../c-runtime-library/reference/fsetpos.md)|Akışın kümesi konumu göstergesi|  
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Dosya paylaşımı açık akış|  
|[ftell, _ftelli64](../c-runtime-library/reference/ftell-ftelli64.md)|Geçerli dosya konumu Al|  
|[fwrite](../c-runtime-library/reference/fwrite.md)|Akış için biçimlendirilmemiş veri öğesi yazma|  
|[getc, getwc](../c-runtime-library/reference/getc-getwc.md)|Karakter akışından okuma (makrosu sürümlerini `fgetc` ve `fgetwc`)|  
|[getchar, getwchar](../c-runtime-library/reference/getc-getwc.md)|Karakter okuma `stdin` (makrosu sürümlerini `fgetchar` ve `fgetwchar`)|  
|[_getmaxstdio](../c-runtime-library/reference/getmaxstdio.md)|Akış g/ç düzeyi izin verilen eşzamanlı olarak açık dosyaların sayısını döndürür.|  
|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|Satırından okuma`stdin`|  
|[_getw](../c-runtime-library/reference/getw.md)|Okuma ikili `int` akıştan|  
|[Printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Biçimlendirilmiş verileri yazma`stdout`|  
|[putc, putwc](../c-runtime-library/reference/putc-putwc.md)|Bir akışa karakter yazma (makrosu sürümlerini `fputc` ve `fputwc`)|  
|[putchar, putwchar](../c-runtime-library/reference/putc-putwc.md)|Karakter yazma `stdout` (makrosu sürümlerini `fputchar` ve `fputwchar`)|  
|[puts, _putws](../c-runtime-library/reference/puts-putws.md)|Akışa satır yazın|  
|[_putw](../c-runtime-library/reference/putw.md)|İkili yazma `int` akış|  
|[rewind](../c-runtime-library/reference/rewind.md)|Dosya konumu akışının başlangıcına Taşı|  
|[_rmtmp](../c-runtime-library/reference/rmtmp.md)|Tarafından oluşturulan geçici dosyaları kaldırma`tmpfile`|  
|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Verileri okuma biçimlendirilmiş`stdin`|  
|[setbuf](../c-runtime-library/reference/setbuf.md)|Denetim akışı arabelleğe alma|  
|[_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md)|Aynı anda açık dosya sayısı için üst sınır akış g/ç düzeyini ayarlayın.|  
|[setvbuf](../c-runtime-library/reference/setvbuf.md)|Denetim akışı arabelleğe alma ve arabellek boyutu|  
|[_snprintf, _snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|Belirtilen uzunlukta biçimlendirilmiş veriler dizeye yazma|  
|[_snscanf, _snwscanf](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md), [_snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Verileri belirtilen uzunlukta standart giriş akışından okuma biçimlendirilmiş.|  
|[sprintf, swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Biçimlendirilmiş verileri dizeye yazma|  
|[sscanf, swscanf](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md), [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|Dize verilerini okuma biçimlendirilmiş|  
|[_tempnam, _wtempnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|Geçici dosya adı oluşturmak dizin verilen|  
|[tmpfile](../c-runtime-library/reference/tmpfile.md), [tmpfile_s](../c-runtime-library/reference/tmpfile-s.md)|Geçici dosya oluşturma|  
|[tmpnam, _wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), [tmpnam_s, _wtmpnam_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|Geçici dosya adı oluştur|  
|[ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)|Karakter akışa geri itme|  
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md), [_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|Biçimlendirilmiş verileri konsola yazar.|  
|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|Biçimlendirilmiş verileri akışına yazma|  
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md), [vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|Biçimlendirilmiş verileri yazma`stdout`|  
|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md), [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Belirtilen uzunlukta biçimlendirilmiş veriler arabelleğe yazma|  
|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md), [vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|Biçimlendirilmiş veriler arabelleğe yazma|  
  
 Bir program yürütme başladığında, başlangıç kodu otomatik olarak birkaç akışları açılır: standart giriş (gösterdiği `stdin`), standart çıkış (gösterdiği `stdout`) ve standart hata (gösterdiği `stderr`). Bu akışlar (klavye ve ekran) konsola varsayılan olarak yönlendirilir. Kullanım `freopen` yönlendirmek için `stdin`, `stdout`, veya `stderr` bir disk dosyası veya bir aygıt.  
  
 Akış yordamları kullanarak açılan dosyaları varsayılan olarak arabelleğe alınmamış. `stdout` Ve `stderr` işlevleri tam olduğunda veya her kitaplık çağrısından sonra bir karakter cihaza yazıyorsanız temizlendi. Bir program sonlandırılırsa çıktı, veri kaybına neden kopyalanması önyükleme değil. Kullanım `fflush` veya `_flushall` belirtilen bir dosyayla ilişkili arabellek veya açık olan tüm arabellekler verileri diske yazmadan önce önbellekte işletim sistemine Temizlenen emin olmak için. Commit-to-disk özellik temizlenmiş arabellek içeriği bir sistem hatası durumunda kaybedilmemesini sağlar.  
  
 Arabellek içeriği diske kaydetmek için iki yolu vardır:  
  
-   Dosyayı COMMODE ile ilişkilendirin. OBJ genel tamamlama bayrağı ayarlanamadı. Varsayılan ayar genel bayrağı `n`, için "Hayır-commit."  
  
-   Modu bayrağını ayarlayın `c` ile `fopen` veya `_fdopen`.  
  
 Herhangi bir dosyayı özellikle açılan biriyle `c` veya `n` bayrağı davranır genel Hayır/commit-commit bayrağının durumunu bakılmaksızın bayrağı göre.  
  
 Bir akış programınızı açıkça kapatmaz, program sonlandırıldığında akış otomatik olarak kapatılır. Ancak, programınız onunla tamamlandığında, bir kerede açılabilir akış sayısı sınırlı olduğu gibi bir akış kapatmalısınız. Bkz: [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) bu sınırı hakkında bilgi için.  
  
 Giriş yalnızca bir araya giren çağrısı ile doğrudan çıktı izleyin `fflush` veya dosya konumlandırma işlevi (`fseek`, `fsetpos`, veya `rewind`). Giriş işlemi dosyasının sonuna karşılaşırsa çıkış girişi müdahalede bulunan bir dosya konumlandırma işlevi çağrısı olmadan izleyebilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Giriş ve çıkış](../c-runtime-library/input-and-output.md)   
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)