---
description: 'Daha fazla bilgi edinin: akış g/ç'
title: Akış G/Ç
ms.date: 11/04/2016
helpviewer_keywords:
- I/O routines, stream I/O
- I/O [CRT], stream
- stream I/O
ms.assetid: dc7874d3-a91b-456a-9015-4748bb358217
ms.openlocfilehash: a787d83390239679ad48c2ca09b41f567a0a8c95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235677"
---
# <a name="stream-io"></a>Akış G/Ç

Bu işlevler, verileri farklı boyutlarda ve biçimlerdeki, tek karakterlerden büyük veri yapılarına işler. Ayrıca, arabelleğe alma da sağlar ve bu da performansı iyileştirebilir. Akış arabelleğinin varsayılan boyutu 4K 'dir. Bu yordamlar yalnızca çalışma zamanı kitaplığı yordamları tarafından oluşturulan arabellekleri etkiler ve işletim sistemi tarafından oluşturulan arabelleklere hiçbir etkiye sahip olmaz.

## <a name="stream-io-routines"></a>Akış g/ç yordamları

|Yordam|Kullanın|
|-------------|---------|
|[clearerr](../c-runtime-library/reference/clearerr.md), [clearerr_s](../c-runtime-library/reference/clearerr-s.md)|Akış için hata göstergesini temizle|
|[fclose](../c-runtime-library/reference/fclose-fcloseall.md)|Akışı kapat|
|[_fcloseall](../c-runtime-library/reference/fclose-fcloseall.md)|**STDIN**, **stdout** ve **stderr** hariç tüm açık akışları kapat|
|[_fdopen, wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)|Akışı açık dosyanın dosya tanımlayıcısıyla ilişkilendir|
|[feof](../c-runtime-library/reference/feof.md)|Akışta dosya sonu için test|
|[ferror](../c-runtime-library/reference/ferror.md)|Akışta hata için test|
|[fflush](../c-runtime-library/reference/fflush.md)|Akışı arabelleğe veya depolama cihazına Temizleme|
|[fgetc, fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md)|Akıştan karakter oku ( **getc** ve **getwc** işlevinin işlev sürümleri)|
|[_fgetchar, _fgetwchar](../c-runtime-library/reference/fgetc-fgetwc.md)|**STDIN** 'den karakter oku ( **GetChar** ve **getwchar** işlev sürümleri)|
|[fgetpos](../c-runtime-library/reference/fgetpos.md)|Akışın konum göstergesini al|
|[fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)|Akıştan dize oku|
|[_fileno](../c-runtime-library/reference/fileno.md)|Stream ile ilişkili dosya tanımlayıcısını al|
|[_flushall](../c-runtime-library/reference/flushall.md)|Tüm akışları arabelleğe veya depolama cihazına yasla|
|[fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md), [fopen_s _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md)|Akışı aç|
|[fprintf, _fprintf_l, fwprintf, _fwprintf_l](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)|Biçimli verileri akışa yaz|
|[fputc, fputwc](../c-runtime-library/reference/fputc-fputwc.md)|Akışa bir karakter yazma ( **putc** ve **putwc** işlev sürümleri)|
|[_fputchar, _fputwchar](../c-runtime-library/reference/fputc-fputwc.md)|**Stdout** 'a karakter yazma ( **putchar** ve **putwchar** işlev sürümleri)|
|[fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)|Akışa dize yaz|
|[fread](../c-runtime-library/reference/fread.md)|Akıştan biçimlendirilmemiş verileri oku|
|[serbest açık, _wfreopen](../c-runtime-library/reference/freopen-wfreopen.md), [freopen_s _wfreopen_s](../c-runtime-library/reference/freopen-s-wfreopen-s.md)|**Dosya** akışı işaretçisini yeni dosya veya cihaza yeniden ata|
|[fscanf, fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)|Akıştan biçimlendirilen verileri oku|
|[fseek, _fseeki64](../c-runtime-library/reference/fseek-fseeki64.md)|Dosya konumunu belirtilen konuma taşı|
|[fsetpos](../c-runtime-library/reference/fsetpos.md)|Akışın konum göstergesini ayarla|
|[_fsopen, _wfsopen](../c-runtime-library/reference/fsopen-wfsopen.md)|Dosya paylaşımı ile açık akış|
|[ftell, _ftelli64](../c-runtime-library/reference/ftell-ftelli64.md)|Geçerli dosya konumunu al|
|[fwrite](../c-runtime-library/reference/fwrite.md)|Biçimlendirilmemiş veri öğelerini akışa yaz|
|[getc, getwc](../c-runtime-library/reference/getc-getwc.md)|Akıştan karakter oku ( **fgetc** ve **fgetwc** makro sürümleri)|
|[getchar, getwchar](../c-runtime-library/reference/getc-getwc.md)|**Stdin** 'den karakter oku ( **fgetchar** ve **fgetwchar** makro sürümleri)|
|[_getmaxstdio](../c-runtime-library/reference/getmaxstdio.md)|Akış g/ç düzeyinde izin verilen aynı anda açık dosya sayısını döndürür.|
|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|**STDIN** 'den satırı oku|
|[_getw](../c-runtime-library/reference/getw.md)|Akıştan binary oku **`int`**|
|[printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),[printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)|**Stdout** 'a biçimlendirilen verileri yazma|
|[putc, putwc](../c-runtime-library/reference/putc-putwc.md)|Akışa karakter yazma ( **fputc** ve **fputwc** makro sürümleri)|
|[putchar, putwchar](../c-runtime-library/reference/putc-putwc.md)|**Stdout** 'a karakter yazma ( **fputchar** ve **fputwchar** makro sürümleri)|
|[puts, _putws](../c-runtime-library/reference/puts-putws.md)|Satırı akışa yaz|
|[_putw](../c-runtime-library/reference/putw.md)|İkiliden **`int`** akışa yazma|
|[geri sar](../c-runtime-library/reference/rewind.md)|Dosya konumunu akışın başına taşı|
|[_rmtmp](../c-runtime-library/reference/rmtmp.md)|**Tmpfile** tarafından oluşturulan geçici dosyaları Kaldır|
|[scanf, _scanf_l, wscanf, _wscanf_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)|**STDIN** 'den biçimlendirilen verileri okuma|
|[setbuf](../c-runtime-library/reference/setbuf.md)|Denetim akışı arabelleğe alma|
|[_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md)|Akış g/ç düzeyinde aynı anda açık dosya sayısı için bir maksimum değer ayarlayın.|
|[setvbuf](../c-runtime-library/reference/setvbuf.md)|Denetim akışı arabelleğe alma ve arabellek boyutu|
|[_snprintf, _snwprintf](../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md), [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)|Belirtilen uzunlukla biçimlendirilen verileri dizeye yaz|
|[_snscanf, _snwscanf](../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md), [_snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l](../c-runtime-library/reference/snscanf-s-snscanf-s-l-snwscanf-s-snwscanf-s-l.md)|Standart giriş akışından belirtilen uzunluktaki biçimlendirilen verileri okuyun.|
|[sprintf, swprintf](../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md), [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](../c-runtime-library/reference/sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md)|Biçimlendirilen verileri dizeye yaz|
|[sscanf, swscanf](../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md), [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)|Dizeden biçimlendirilen verileri oku|
|[_tempnam, _wtempnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)|Verilen dizinde geçici dosya adı oluştur|
|[tmpfile](../c-runtime-library/reference/tmpfile.md), [tmpfile_s](../c-runtime-library/reference/tmpfile-s.md)|Geçici dosya oluştur|
|[tmpnam, _wtmpnam](../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md), [tmpnam_s, _wtmpnam_s](../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md)|Geçici dosya adı oluştur|
|[ungetc, ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)|Karakteri akışa geri gönder|
|[_vcprintf, _vcwprintf](../c-runtime-library/reference/vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md), [_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l](../c-runtime-library/reference/vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md)|Biçimli verileri konsola yazın.|
|[vfprintf, vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vfprintf_s, _vfprintf_s_l, vfwprintf_s, _vfwprintf_s_l](../c-runtime-library/reference/vfprintf-s-vfprintf-s-l-vfwprintf-s-vfwprintf-s-l.md)|Biçimli verileri akışa yaz|
|[vprintf, öprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md), [vprintf_s, _vprintf_s_l, vwprintf_s, _vwprintf_s_l](../c-runtime-library/reference/vprintf-s-vprintf-s-l-vwprintf-s-vwprintf-s-l.md)|**Stdout** 'a biçimlendirilen verileri yazma|
|[_vsnprintf, _vsnwprintf](../c-runtime-library/reference/vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md), [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)|Belirtilen uzunlukta biçimlendirilen verileri arabelleğe yaz|
|[vsprintf, vswprintf](../c-runtime-library/reference/vsprintf-vsprintf-l-vswprintf-vswprintf-l-vswprintf-l.md), [vsprintf_s, _vsprintf_s_l, vswprintf_s, _vswprintf_s_l](../c-runtime-library/reference/vsprintf-s-vsprintf-s-l-vswprintf-s-vswprintf-s-l.md)|Biçimlendirilen verileri arabelleğe yaz|

Bir program yürütmeye başladığında, başlangıç kodu birkaç akışı otomatik olarak açar: standart giriş ( **stdin** tarafından işaret edilen), standart çıkış ( **stdout** tarafından işaret edilen) ve standart hata ( **stderr** tarafından işaret edilen). Bu akışlar, varsayılan olarak konsola (klavye ve ekran) yönlendirilir. **STDIN**, **stdout** veya **stderr** 'i bir disk dosyasına veya cihaza yeniden yönlendirmek için **freopen** 'ı kullanın.

Akış yordamları kullanılarak açılan dosyalar varsayılan olarak arabelleğe alınır. **Stdout** ve **stderr** işlevleri her dolduğunda silinir veya bir karakter cihazına yazıyorsanız, her kitaplık çağrısından sonra temizlenir. Bir program anormal bir şekilde sonlandırılırsa, çıkış arabellekleri temizlenmeyebilir ve veri kaybına neden olabilir. Belirtilen bir dosyayla ilişkili arabelleğin veya tüm açık arabelleklerin işletim sistemine temizlendiğinden emin olmak için **fflush** veya **_flushall** kullanın. Bu, verileri diske yazmadan önce önbelleğe alabilir. Diske Yürüt özelliği, bir sistem hatası durumunda boşaltılan arabellek içeriğinin kaybolmamasını sağlar.

Arabellek içeriğini diske kaydetmenin iki yolu vardır:

- Dosya COMMODE ile bağlantı. OBJ bir genel COMMIT bayrağı ayarlamak için. "No-COMMIT" için genel bayrağın varsayılan ayarı **n**' dir.

- Mode bayrağını **fopen** veya **_fdopen** ile **c** olarak ayarlayın.

Özellikle **c** veya **n** bayrağıyla açılan herhangi bir dosya, Genel tamamlama/No-COMMIT bayrağının durumundan bağımsız olarak, bayrağa göre davranır.

Programınız bir akışı açıkça kapatmadıysa, program sonlandırıldığında akış otomatik olarak kapatılır. Ancak, bir kerede açık olabilecek akışların sayısı sınırlı olduğundan, programınız onunla bittiğinde bir akışı kapatmanız gerekir. Bu limit hakkında bilgi için bkz. [_setmaxstdio](../c-runtime-library/reference/setmaxstdio.md) .

Giriş yalnızca bir **fflush** veya dosya konumlandırma işlevine (**fseek**, **fsetpos** veya **geri sarma**) aradaki bir çağrı ile doğrudan çıktıyı izleyebilir. Giriş işlemi dosyanın sonuyla karşılaştığında, çıkış bir dosya konumlandırma işlevine araya giren bir çağrı olmadan girişi izleyebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Giriş ve çıkış](../c-runtime-library/input-and-output.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
