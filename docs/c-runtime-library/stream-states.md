---
description: 'Daha fazla bilgi edinin: Stream durumları'
title: Akış Durumları
ms.date: 11/19/2018
helpviewer_keywords:
- streams, states
ms.assetid: 5f28c968-f132-403f-968c-8417ff315e52
ms.openlocfilehash: c691c1fd01feb9f78ff0929775505f08cb625ecc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224185"
---
# <a name="stream-states"></a>Akış Durumları

Bir akış için geçerli durumlar ve durum geçişleri aşağıdaki şekilde gösterilmiştir.

![Akış durumu diyagramı](../c-runtime-library/media/stream.gif "Akış durumu diyagramı")

Dairelerin her biri kararlı bir durumu gösterir. Her satır, akışta çalışan bir işlev çağrısının sonucu olarak gerçekleşebileceği bir geçişi gösterir. Beş işlev grubu durum geçişlerine neden olabilir.

İlk üç grubun işlevleri içinde bildirilmiştir \<stdio.h> :

- Bayt okuma işlevleri — [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), [fal](../c-runtime-library/reference/fgets-fgetws.md), [fread](../c-runtime-library/reference/fread.md), [fscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getc](../c-runtime-library/reference/getc-getwc.md), [GetChar](../c-runtime-library/reference/getc-getwc.md), [Al](../c-runtime-library/gets-getws.md), [scanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)ve [ungetc](../c-runtime-library/reference/ungetc-ungetwc.md)

- Bayt yazma işlevleri: [fprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputc](../c-runtime-library/reference/fputc-fputwc.md), [fkoyar](../c-runtime-library/reference/fputs-fputws.md), [fwrite](../c-runtime-library/reference/fwrite.md), [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md), [putc](../c-runtime-library/reference/putc-putwc.md), [putchar](../c-runtime-library/reference/putc-putwc.md), [koyar](../c-runtime-library/reference/puts-putws.md), [vfprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md)ve [vprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)

- Position işlevleri — [fflush](../c-runtime-library/reference/fflush.md), [fseek](../c-runtime-library/reference/fseek-fseeki64.md), [fsetpos](../c-runtime-library/reference/fsetpos.md)ve [geri sarma](../c-runtime-library/reference/rewind.md)

Kalan iki grubun işlevleri içinde bildirilmiştir \<wchar.h> :

- Geniş okuma işlevleri — [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), [fgetws](../c-runtime-library/reference/fgets-fgetws.md), [fwscanf](../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md), [getwc](../c-runtime-library/reference/getc-getwc.md), [getwchar](../c-runtime-library/reference/getc-getwc.md), [ungetwc](../c-runtime-library/reference/ungetc-ungetwc.md)ve [wscanf](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md),

- Geniş yazma işlevleri — [fwprintf](../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md), [fputwc](../c-runtime-library/reference/fputc-fputwc.md), [fputws](../c-runtime-library/reference/fputs-fputws.md), [putwc](../c-runtime-library/reference/putc-putwc.md), [putwchar](../c-runtime-library/reference/fputc-fputwc.md), [vfwprintf](../c-runtime-library/reference/vfprintf-vfprintf-l-vfwprintf-vfwprintf-l.md), [eprintf](../c-runtime-library/reference/vprintf-vprintf-l-vwprintf-vwprintf-l.md)ve [wprintf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md),

Durum diyagramı, en fazla yazma ve okuma işlemi arasındaki konum işlevlerinden birini çağırmanız gerektiğini gösterir:

- Akıştaki son işlem bir yazma işlemi ise Read işlevi çağrılamaz.

- Okuma işlemi dosya sonu göstergesini ayarlayamadığı takdirde akıştaki son işlem bir okuma ise, yazma işlevi çağrılamaz.

Son olarak, durum diyagramı bir konum işleminin izleyene geçerli işlev çağrılarının sayısını hiçbir şekilde azaltmayacağını gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar ve akışlar](../c-runtime-library/files-and-streams.md)
