---
title: Akış Durumları
ms.date: 11/04/2016
helpviewer_keywords:
- streams, states
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
ms.openlocfilehash: d51f24b82c10d58e91f5d20b6656eb16621004ac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481178"
---
# <a name="stream-states"></a>Akış Durumları

Geçerli durumları ve durum geçişlerini, bir akış için aşağıdaki şekilde gösterilmektedir.

![Stream](../c-runtime-library/media/stream.gif "akış")

Her dairelerin kararlı bir duruma gösterir. Satırların her biri, akışta işleyen bir işlev çağrısının sonucu olarak ortaya çıkabilecek geçiş gösterir. İşlevlerin beş grup durumu geçişleri neden olabilir.

İlk üç gruplardaki işlevler içinde bildirilen \<stdio.h >:

- İşlevleri bayt okuma — [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc](../c-runtime-library/reference/getc-getwc.md), [ getchar](../c-runtime-library/reference/getc-getwc.md), [alır](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), ve [ungetc](../c-runtime-library/reference/ungetc-ungetwc.md)

- Bayt yazma işlevleri — [fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fputs](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [koyar](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), ve [vprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)

- Konum işlevleri — [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md), ve [Geri Sar](../c-runtime-library/reference/rewind.md)

Kalan iki grup işlevler içinde bildirilen \<wchar.h >:

- İşlevleri geniş okuma — [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md), ve [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),

- Geniş yazma işlevleri — [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md), ve [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),

Çoğu yazma ve okuma işlemleri arasında konumu işlevlerden birini çağırmalıdır durumu diyagramını gösterir:

- Akışın son işlemi yazma olduysa salt okunur bir işlev çağrılamaz.

- Akışın son işlemi okuma, varsa, dosya sonu göstergesi ayarlama işlemi okuma yazma işlevi çağrılamıyor.

Son olarak, bir konum işlemi hiçbir zaman izleyebileceğiniz geçerli işlev çağrılarının sayısını azaltır durumu diyagramını gösterir.

## <a name="see-also"></a>Ayrıca Bkz.

[Dosyalar ve Akışlar](../c-runtime-library/files-and-streams.md)