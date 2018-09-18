---
title: Dosyalar ve akışlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- files [C++]
- streams
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ca0850f0e798067ba48b59a1c2585b8ba87c5451
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46062182"
---
# <a name="files-and-streams"></a>Dosyalar ve Akışlar

Bir program, okuma ve yazma, hedef ortam ile iletişim kurar. Bir dosya olabilir:

- Veri okuma ve yazma sürekli olarak ayarlayın.

- Bir program (örneğin, bir işlem hattı) tarafından oluşturulan bayt akışı.

- Bayt akışı bir aygıttaki gönderilen veya alınan.

Son iki öğeyi etkileşimli dosyalarıdır. Genellikle, bir programla etkileşim kurmasına asıl yöntemlerle dosyalarıdır. Bu tür dosyaların çok aynı şekilde işlemek — kitaplık işlevleri çağırarak. Standart üst bilgi STDIO dahil. Bu işlevlerin çoğunu bildirmek için H.

Birçok dosya üzerindeki işlemler gerçekleştirmek için önce dosyanın açılması gerekir. Dosya açma stream, çeşitli türlerdeki dosyaları arasında pek çok fark üzerinden glosses standart C Kitaplığı içinde bir veri yapısı ile ilişkilendirir. Kitaplığa dosya türünde bir nesne içindeki her akış durumu korur.

Hedef ortamı, program başlatma önce üç dosyayı açar. Kitaplık işlevini çağırarak bir dosyayı açabilirsiniz [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) iki bağımsız değişken. ( `fopen` İşlevi kullanımdan kaldırıldı, kullanın [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) yerine.) İlk bağımsız değişkeni bir dosya adıdır. İkinci bağımsız değişkeni belirten C dize şöyledir:

- İster veri dosyasından verileri okuma veya bunu veya her ikisini de yazma sunmayı planlıyoruz.

- Dosya için yeni içerik oluştur (veya daha önce mevcut bir dosya oluşturun) istediğinize veya var olan içeriğin yerinde bırakın.

- Olup bir dosyaya yazma mevcut içeriğini değiştirebilir veya yalnızca dosyanın sonunda bayt eklemeniz gerekir.

- Metin akışına veya ikili akışa değiştirmek isteyip istemediğinizi.

Dosya başarıyla açıldıktan sonra ardından akış odaklı bayt (bayt akışı) olup olmadığını belirlemek veya geniş (geniş bir akışı) yönelik. Başlangıçta ilişkisiz bir akış biçimindedir. Akışta çalışmak için bazı işlevlerini çağırma yönelik belirli diğer işlevleri yönelik geniş bunu yaparken bayt yapar. Bir çağrı tarafından kapatılana kadar kez kurulduğunda, bir akış yönünü korur [fclose](../c-runtime-library/reference/fclose-fcloseall.md) veya [freopen](../c-runtime-library/reference/freopen-wfreopen.md).

© 2001 1989 tarafından hazırlanan Plauger ve Jim Brodie. Tüm hakları saklıdır.

## <a name="see-also"></a>Ayrıca Bkz.

[Metin ve İkili Akışlar](../c-runtime-library/text-and-binary-streams.md)<br/>
[Bayt ve Geniş Akışlar](../c-runtime-library/byte-and-wide-streams.md)<br/>
[Akışları Denetleme](../c-runtime-library/controlling-streams.md)<br/>
[Akış Durumları](../c-runtime-library/stream-states.md)