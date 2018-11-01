---
title: Akış G/Ç
ms.date: 11/04/2016
f1_keywords:
- c.io
helpviewer_keywords:
- I/O routines, stream I/O
- I/O [CRT], stream
- stream I/O
ms.assetid: dc7874d3-a91b-456a-9015-4748bb358217
ms.openlocfilehash: 097019b2299ad4d2563b5e0df1b943d190b16197
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442646"
---
# <a name="stream-io"></a>Akış G/Ç

Bu işlevler, farklı boyutlarda ve büyük veri yapıları için tek karakterleri biçimlerinden verilerini işler. Ayrıca arabelleğe alma, performansın iyileşmesini sağlayabilecek sağlarlar. Bir akış arabelleğinin varsayılan boyutu 4 K'dır. Bu yordamlar, yalnızca çalışma zamanı kitaplık yordamları tarafından oluşturulan arabellekler etkiler ve işletim sistemi tarafından oluşturulan arabellekler üzerinde hiçbir etkisi yoktur.

## <a name="stream-io-routines"></a>Stream g/ç yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[clearerr](../c-runtime-library/reference/clearerr.md), [clearerr_s](../c-runtime-library/reference/clearerr-s.md)|Akış için açık bir hata göstergesi|
|[fclose](../c-runtime-library/reference/fclose-fcloseall.md)|Akışı Kapat|
|[_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)|Dışındaki tüm açık akışları kapatmak **stdin**, **stdout**, ve **stderr**|
|[_fdopen, wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Stream açık bir dosyanın dosya tanımlayıcısı ile ilişkilendirme|
|[feof](../c-runtime-library/reference/feof.md)|Dosya akışında sonu için sınama|
|[ferror](../c-runtime-library/reference/ferror.md)|Akış hatası için test etme|
|[fflush](../c-runtime-library/reference/fflush.md)|Akış Arabellek veya depolama cihazı temizler.|
|[fgetc, fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md)|Karakter akıştan okunan (işlev sürümleri **getc** ve **getwc**)|
|[_fgetchar, _fgetwchar](../c-runtime-library/reference/fgetc-fgetwc.md)|Okuma karakteri **stdin** (işlev sürümleri **getchar** ve **getwchar**)|
|[fgetpos](../c-runtime-library/reference/fgetpos.md)|Akış konumu göstergesi Al|
|[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)|Akıştan okunan dizisi|
|[_fileno](../c-runtime-library/reference/fileno.md)|Stream ile ilişkili dosya tanımlayıcısı Al|
|[_flushall](../c-runtime-library/reference/flushall.md)|Arabellek veya depolama cihazı için tüm akışları temizleme|
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Açma işlemi|
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|Biçimlendirilmiş veri akışına yazma|
|[fputc, fputwc](../c-runtime-library/reference/fputc-fputwc.md)|Bir akışa bir karakter yazın (işlev sürümleri **putc** ve **putwc**)|
|[_fputchar, _fputwchar](../c-runtime-library/reference/fputc-fputwc.md)|Yazma karakteri **stdout** (işlev sürümleri **putchar** ve **putwchar**)|
|[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)|Dize akışına yazar.|
|[fread](../c-runtime-library/reference/fread.md)|Biçimlendirilmemiş veri akışından okuma|
|[freopen, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s, _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|Yeniden atama **dosya** yeni dosya veya cihaza akış işaretçisini|
|[fscanf, fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|Biçimlendirilmiş verileri akışından okuma|
|[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)|Konuma taşı dosya konumuna verilen|
|[fsetpos](../c-runtime-library/reference/fsetpos.md)|Akış kümesi Konum göstergesi|
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Dosya Paylaşımı ile açık akış|
|[ftell, _ftelli64](../c-runtime-library/reference/ftell-ftelli64.md)|Geçerli dosya konumu Al|
|[fwrite](../c-runtime-library/reference/fwrite.md)|Akış için biçimlendirilmemiş veri öğesi yazma|
|[getc, getwc](../c-runtime-library/reference/getc-getwc.md)|Karakter akıştan okunan (makro sürümleri **fgetc** ve **fgetwc**)|
|[getchar, getwchar](../c-runtime-library/reference/getc-getwc.md)|Okuma karakteri **stdin** (makro sürümleri **fgetchar** ve **fgetwchar**)|
|[_getmaxstdio](../c-runtime-library/reference/getmaxstdio.md)|Akış g/ç düzeyi izin verilen eşzamanlı olarak açık dosyaların sayısını döndürür.|
|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|Satırı oku **stdin**|
|[_getw](../c-runtime-library/reference/getw.md)|Okuma ikili **int** akışından|
|[Printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|Biçimlendirilmiş verileri yazma **stdout**|
|[putc, putwc](../c-runtime-library/reference/putc-putwc.md)|Bir akışa karakteri yazın (makro sürümleri **fputc** ve **fputwc**)|
|[putchar, putwchar](../c-runtime-library/reference/putc-putwc.md)|Yazma karakteri **stdout** (makro sürümleri **fputchar** ve **fputwchar**)|
|[puts, _putws](../c-runtime-library/reference/puts-putws.md)|Satır akışına yazar.|
|[_putw](../c-runtime-library/reference/putw.md)|İkiliyi yazmaya **int** akış|
|[rewind](../c-runtime-library/reference/rewind.md)|Dosya konumu akış başlangıcına Taşı|
|[_rmtmp](../c-runtime-library/reference/rmtmp.md)|Tarafından oluşturulan geçici dosyalar kaldırmak **tmpfile**|
|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|Biçimlendirilmiş verileri okuma **stdin**|
|[setbuf](../c-runtime-library/reference/setbuf.md)|Denetim akışı arabelleğe alma|
|[_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md)|Aynı anda açık dosya sayısı için en fazla akış g/ç düzeyini ayarlayın.|
|[setvbuf](../c-runtime-library/reference/setvbuf.md)|Denetim akışı arabelleğe alma ve arabellek boyutu|
|[_snprintf, _snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|Dize olarak belirtilen uzunlukta biçimlendirilmiş veri yazma|
|[_snscanf, _snwscanf](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md), [_snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Okuma biçimlendirilmiş verileri standart giriş akışından belirtilen uzunlukta.|
|[sprintf, swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Dize olarak biçimlendirilmiş veri yazma|
|[sscanf, swscanf](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md), [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|Biçimlendirilmiş dize değerinden verileri okuma|
|[_tempnam, _wtempnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|Geçici dosya oluşturmak verilen dizini|
|[tmpfile](../c-runtime-library/reference/tmpfile.md), [tmpfile_s](../c-runtime-library/reference/tmpfile-s.md)|Geçici dosya oluşturma|
|[tmpnam, _wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), [tmpnam_s, _wtmpnam_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|Geçici dosya adı oluştur|
|[ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)|Karakteri akışa geri itme|
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md), [_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|Biçimlendirilmiş verileri konsola yazar.|
|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|Biçimlendirilmiş veri akışına yazma|
|[vprintf, vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md), [vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|Biçimlendirilmiş verileri yazma **stdout**|
|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md), [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Belirtilen uzunlukta biçimlendirilmiş veri arabelleği için yazma|
|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md), [vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|Biçimlendirilmiş veri arabelleği için yazma|

Bir program yürütme başladığında, başlangıç kodu birkaç akışları otomatik olarak açılır.: standart giriş (işaret ettiği **stdin**), standart çıkış (işaret ettiği **stdout**) ve standart hata (işaret ettiği **stderr**). Bu akışları varsayılan olarak (klavye ve ekran) konsoluna yönlendirilirsiniz. Kullanım **freopen** yönlendirmek için **stdin**, **stdout**, veya **stderr** bir disk dosyası veya bir cihaz.

Stream yordamları kullanarak açılan dosyaları varsayılan olarak arabelleğe alınır. **Stdout** ve **stderr** işlevleri tam olduğunda veya bir karakter cihaza her kitaplık çağrısından sonra yazıyorsanız temizlendi. Bir program anormal olarak sona ererse, çıkış, veri kaybıyla sonuçlanan kopyalanması önyükleme değil. Kullanım **fflush** veya **_flushall** belirtilen bir dosya ile ilişkilendirilmiş arabellek veya açık olan tüm arabellekler verileri diske yazmadan önce önbelleğe işletim sistemine aktarıldığından emin olmak için. Temizlenmiş arabellek içeriği bir sistem hatası durumunda kaybolmamasını diske işleme özelliği sağlar.

Arabellek içeriği diske kaydetmek için iki yolu vardır:

- Dosyayı COMMODE ile ilişkilendirin. OBJ bir küresel kaydetme bayrağı ayarlanamadı. Genel Bayrak varsayılan ayardır **n**, için "no-commit."

- Modu bayrağını ayarlayın **c** ile **fopen** veya **_fdopen**.

Herhangi bir dosya özel olarak açılmış ile **c** veya **n** bayrağı davranışını göre genel işleme/no-commit bayrak durumundan bağımsız olarak bayrak.

Programınız bir akış açıkça kapatmazsa akış program sonlandığında otomatik olarak kapatılır. Ancak, programınızı onunla tamamlandığında tek seferde açılabilir akışları sayısı sınırlı olduğu gibi bir akış kapatmalısınız. Bkz: [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) bu sınırlar hakkında daha fazla bilgi için.

Giriş, çıkış yalnızca bir çağrı göndermelisiniz ile doğrudan izleyebilirsiniz **fflush** veya dosyada konumlanma işleve (**fseek**, **fsetpos**, veya **GeriSar**). Giriş işlemi dosyanın sonuna karşılaşırsa, bir dosyada konumlanma işlevine bir çağrı göndermelisiniz olmadan giriş çıkış izleyebilirsiniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Girdi ve Çıktı](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
