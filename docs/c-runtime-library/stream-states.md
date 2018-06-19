---
title: Akış durumları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- streams, states
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 418ed7c98523bf8944afcccc13a0e9020036940f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413142"
---
# <a name="stream-states"></a>Akış Durumları
Geçerli durumları ve bir akış için durumu geçişleri aşağıdaki çizimde gösterilmektedir.  
  
 ![Akış](../c-runtime-library/media/stream.gif "akış")  
  
 Her daireleri kararlı bir duruma gösterir. Her satır bir akış üzerinde çalıştığı bir işlev çağrısı sonucu olarak ortaya çıkabilecek geçiş gösterir. İşlevlerin beş grup durumu geçişleri neden olabilir.  
  
 İlk üç gruplarındaki işlevler içinde bildirilen \<stdio.h >:  
  
-   İşlevler bayt okuma — [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgets](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc](../c-runtime-library/reference/getc-getwc.md), [ getchar](../c-runtime-library/reference/getc-getwc.md), [alır](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md), ve [ungetc](../c-runtime-library/reference/ungetc-ungetwc.md)  
  
-   Bayt yazma işlevlerinin — [fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fputs](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [koyar](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), ve [vprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)  
  
-   Konum işlevleri — [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md), ve [Geri Sar](../c-runtime-library/reference/rewind.md)  
  
 Kalan iki gruplarındaki işlevler içinde bildirilen \<wchar.h >:  
  
-   Wide işlevleri okuma — [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md), ve [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),  
  
-   Wide yazma işlevlerinin — [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [vwprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md), ve [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),  
  
 Çoğu yazma ve okuma işlemleri arasında konumu işlevleri birini çağırmalıdır durumu diyagramı gösterir:  
  
-   Son işlem akışta yazma olduysa okuma işlevi çağrılamaz.  
  
-   Son işlemi akış üzerinde okuma, ise, dosya sonu göstergesi kümesi işlemi okuma sürece yazma işlevi çağrılamaz.  
  
 Son olarak, bir konum işlemi hiçbir zaman izleyebilirsiniz geçerli işlevi çağrılarının sayısı azalır durumu diyagramı gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosyalar ve Akışlar](../c-runtime-library/files-and-streams.md)