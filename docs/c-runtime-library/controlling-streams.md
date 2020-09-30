---
title: Akışları Denetleme
description: Microsoft C çalışma zamanı kitaplığı 'nda akışlarla çalışmaya genel bakış.
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- Controlling Streams
helpviewer_keywords:
- streams, controlling
- controlling streams
- streams
ms.assetid: 267e9013-9afc-45f6-91e3-ca093230d9d9
ms.openlocfilehash: 0caa9eca7c960acbb581358c1a92afcc6a8af066
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589724"
---
# <a name="controlling-streams"></a>Akışları Denetleme

[fopen](../c-runtime-library/reference/fopen-wfopen.md) , türünde bir nesnenin adresini döndürür `FILE` . Bu adresi, `stream` bir açık dosyada çeşitli işlemleri gerçekleştirmek için çeşitli kitaplık işlevlerine bağımsız değişken olarak kullanırsınız. Bir bayt akışı için, her bir karakter [fgetc](../c-runtime-library/reference/fgetc-fgetwc.md)çağırarak okunsa ve tüm çıktılar [fputc](../c-runtime-library/reference/fputc-fputwc.md)çağırarak her bir karakter yazıldıysa, tüm giriş gerçekleşir. Geniş bir akış için, her bir karakter [fgetwc](../c-runtime-library/reference/fgetc-fgetwc.md)çağırarak okunsa ve tüm çıktılar, [fputwc](../c-runtime-library/reference/fputc-fputwc.md)çağırarak her bir karakter yazılsa gibi gerçekleşir.

Bir dosyayı [fclose](../c-runtime-library/reference/fclose-fcloseall.md)çağırarak, sonra `FILE` nesnenin adresinin geçersiz olması için kapatabilirsiniz.

Bir `FILE` nesne, aşağıdakiler dahil olmak üzere akışın durumunu depolar:

- Bir hata göstergesi, okuma veya yazma hatasıyla karşılaştığında bir işlev tarafından sıfır dışında ayarlandı.

- Dosya sonu göstergesi, okurken dosya sonuyla karşılaştığında bir işlev tarafından sıfır dışında ayarlandı.

- Dosya konumu göstergesi, dosya konumlandırma isteklerini destekleyebiliyorsanız, okunan veya yazılacak akıştaki bir sonraki baytı belirtir.

- [Akış durumu](../c-runtime-library/stream-states.md) , akışın okuma ve/veya yazma işlemlerini kabul edip etmediğini ve akışın ilişkisiz, bayt odaklı veya geniş yönelimli olup olmayacağını belirtir.

- Bir dönüştürme durumu, kısmen birleştirilmiş veya üretilen Genelleştirilmiş çok baytlı karakterin durumunu ve dosyadaki bayt sırası için herhangi bir kaydırma durumunu anımsar.

- Dosya arabelleği, kitaplık işlevlerinin akışa yönelik okuma ve yazma işlemlerinin performansını geliştirmek için kullanabileceği bir dizi nesnesinin adresini ve boyutunu belirtir.

Bir `FILE` nesnede veya bu nesneyle birlikte kullanmak üzere belirttiğiniz bir dosya arabelleğinde depolanan herhangi bir değeri değiştirmeyin. Bir `FILE` nesneyi kopyalayamaz ve bir `stream` kitaplık işlevine bağımsız değişken olarak kopya adresini bir bağımsız değişken olarak kullanamazsınız.

## <a name="see-also"></a>Ayrıca bkz.

[Dosyalar ve akışlar](../c-runtime-library/files-and-streams.md)
