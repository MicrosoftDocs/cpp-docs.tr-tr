---
title: Akışları Denetleme
ms.date: 11/04/2016
f1_keywords:
- Controlling Streams
helpviewer_keywords:
- streams, controlling
- controlling streams
- streams
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
ms.openlocfilehash: 85c7e1b22519287fbd03d89487d6639f197a8b63
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344641"
---
# <a name="controlling-streams"></a>Akışları Denetleme

[fopen](../c-runtime-library/reference/fopen-wfopen.md) türünde bir nesnenin adresini döndürür `FILE`. Bu adresi olarak kullanın `stream` açık bir dosya üzerinde çeşitli işlemler gerçekleştirmek için çeşitli kitaplığı işlevler için bağımsız değişken. Her bir karakter çağırarak salt okunursa gibi bayt akışı için tüm giriş gerçekleşir [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md), ve her karakter çağırarak yazıldığı gibi tüm çıktı gerçekleşir [fputc](../c-runtime-library/reference/fputc-fputwc.md). Her bir karakter çağırarak salt okunursa gibi geniş bir akış için tüm giriş gerçekleşir [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md), ve her karakter çağırarak yazıldığı gibi tüm çıktı gerçekleşir [fputwc](../c-runtime-library/reference/fputc-fputwc.md).

Bir dosya çağırarak kapatabilirsiniz [fclose](../c-runtime-library/reference/fclose-fcloseall.md), sonrasında adresini `FILE` nesnesi geçersiz.

A `FILE` nesneyi bir akışa durumunu depolar da dahil olmak üzere:

- Bir hata göstergesi, sıfır olmayan okuma karşılaştığında bir işlev ayarlayın veya yazma hatası.

- Bir dosya sonu göstergesi okunurken dosyasının sonuna karşılaştığında bir işleve göre sıfır olmayan ayarlayın.

- Dosya konumlandırma isteği destekliyorsa bir dosya konumu göstergesi okuma veya yazma, akıştaki sonraki baytı belirtir.

- A [akış durumu](../c-runtime-library/stream-states.md) akış okuma ve/veya yazar ve akış ilişkisiz olup kabul edip etmeyeceğini bayt yönelik veya geniş yönelik belirtir.

- Bir dönüştürme durumu herhangi bir dizi için shift durumu dosyadaki bayt yanı sıra, çok baytlı karakterin herhangi bir araya getirilen ya da kısmen oluşturulan durumunu genelleştirilmiş hatırlar).

- Bir dosyayı arabelleğe kitaplık işlevleri okuma performansını ve işlemleri akışa yazmak için kullanabileceğiniz bir dizi nesnesi boyutunu ve adresini belirtir.

Herhangi bir değeri depolanan değiştirmeyin bir `FILE` nesne veya o nesne ile kullanmak için belirttiğiniz dosya arabelleği. Kopyalanamıyor bir `FILE` nesne ve temelinizi kopya olarak adresini kullanan bir `stream` kitaplığı işlevi bağımsız değişken.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar ve Akışlar](../c-runtime-library/files-and-streams.md)
