---
title: Dosyalar ve Akışlar
ms.date: 11/04/2016
helpviewer_keywords:
- files [C++]
- streams
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
ms.openlocfilehash: ea11ea76ade8a68c2d8a92e08d3652035c996d3d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62343751"
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

## <a name="see-also"></a>Ayrıca bkz.

[Metin ve İkili Akışlar](../c-runtime-library/text-and-binary-streams.md)<br/>
[Bayt ve Geniş Akışlar](../c-runtime-library/byte-and-wide-streams.md)<br/>
[Akışları Denetleme](../c-runtime-library/controlling-streams.md)<br/>
[Akış Durumları](../c-runtime-library/stream-states.md)
