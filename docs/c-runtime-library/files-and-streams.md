---
title: Dosyalar ve Akışlar
description: Microsoft C çalışma zamanı kitaplığı 'ndaki dosyalara ve akışlara genel bakış.
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- files [C++]
- streams
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
ms.openlocfilehash: 39133cfdb4784c42561a159d6d176bcbd23644af
ms.sourcegitcommit: 9451db8480992017c46f9d2df23fb17b503bbe74
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2020
ms.locfileid: "91589971"
---
# <a name="files-and-streams"></a>Dosyalar ve Akışlar

Program, dosyaları okuyarak ve yazarak hedef ortamla iletişim kurar. Bir dosya şu olabilir:

- Okuyabilmeniz ve defalarca yazabileceğiniz bir veri kümesi.

- Bir program tarafından oluşturulan bayt akışı (örneğin, işlem hattı).

- Çevresel bir cihazdan alınan veya gönderilen bayt akışı.

Son iki öğe etkileşimli dosyalardır. Dosyalar genellikle bir programla etkileşimde bulunmak için asıl bir araçtır. Tüm bu dosya türlerini, kitaplık işlevlerini çağırarak, aynı şekilde düzenleyebilirsiniz. STDIO standart üstbilgisini dahil edersiniz. Bu işlevlerin çoğunu bildirmek için H.

Bir dosya üzerinde birçok işlemi gerçekleştirebilmek için önce dosyanın açılması gerekir. Bir dosyayı açmak, standart C kitaplığı içindeki bir veri yapısı olan bir akış ile ilişkilendirir. Bu, çeşitli türlerdeki dosyalar arasında çok fazla farklılık glosses. Kitaplık, her akışın durumunu dosya türünde bir nesne olarak tutar.

Hedef ortam program başlatmadan önce üç dosya açar. Bir dosyayı [, fopen](../c-runtime-library/reference/fopen-wfopen.md) Kitaplık işlevini çağırarak, iki bağımsız değişkenle _wfopen açabilirsiniz. ( `fopen` İşlev kullanım dışı bırakıldı, bunun yerine [fopen_s _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) kullanın.) İlk bağımsız değişken bir dosya adıdır. İkinci bağımsız değişken şunu belirten bir C dizesidir:

- Dosyadan veri okumayı veya veri yazmayı veya her ikisini de ister.

- Dosya için yeni içerik oluşturmayı (veya daha önce yoksa bir dosya oluşturmayı) veya mevcut içeriği yerinde bırakmayı düşünüyorsanız.

- Bir dosyaya yazma işlemleri var olan içerikleri değiştirebilir veya yalnızca dosyanın sonunda baytları eklememe.

- Bir metin akışını veya ikili akışı değiştirmek isteyip istemediğiniz.

Dosya başarıyla açıldıktan sonra akışın bayt odaklı (bayt akışı) veya geniş yönelimli (geniş bir akış) olup olmadığını belirleyebilirsiniz. Bir akışın başlangıçta bağlantısı kesildi. Akış üzerinde çalışmak için belirli işlevleri çağırmak, belirli diğer işlevlerin bu şekilde geniş bir şekilde yönlendirilmesini sağlar. Oluşturulduktan sonra bir akış, bir [fclose](../c-runtime-library/reference/fclose-fcloseall.md) veya [freopen](../c-runtime-library/reference/freopen-wfreopen.md)çağrısı tarafından kapatılana kadar yönünü korur.

© 1989-2001 P.J. Plauger ve Jim Brodie. All rights reserved.

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve Ikili akışlar](../c-runtime-library/text-and-binary-streams.md)<br/>
[Bayt ve geniş akışlar](../c-runtime-library/byte-and-wide-streams.md)<br/>
[Akışları denetleme](../c-runtime-library/controlling-streams.md)<br/>
[Akış durumları](../c-runtime-library/stream-states.md)
