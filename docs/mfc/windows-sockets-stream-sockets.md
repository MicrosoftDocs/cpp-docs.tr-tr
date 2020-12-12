---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: akış Yuvaları'
title: 'Windows Yuvaları: Akış Yuvaları'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
ms.openlocfilehash: b9e40be06ebb1de04466b5f13a46fe82fb3b0bd2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207650"
---
# <a name="windows-sockets-stream-sockets"></a>Windows Yuvaları: Akış Yuvaları

Bu makalede, kullanılabilir iki Windows yuva türünden biri olan akış yuvaları açıklanmaktadır. (Diğer tür, [veri birimi yuvadır](../mfc/windows-sockets-datagram-sockets.md).)

Akış yuvaları, kayıt sınırları olmadan bir veri akışı sağlar: çift yönlü olabilecek bir bayt akışı (uygulama tam çift yönlü) ve yuva aracılığıyla hem aktarabilir hem de alabilir. Akışlara, sıralı, yinelenenleri kaldırılmış veriler teslim etmek için güvenebilirler. ("Sıralı", paketlerin gönderildiği sırada teslim edildiği anlamına gelir. "Yinelenmeyen", belirli bir paketi yalnızca bir kez almanızı gösterir.) Akış iletilerinin alınması garanti edilir ve akışlar, büyük miktarlarda veri işlemeye uygundur.

Ağ aktarım katmanı, verileri makul büyüklükte paketlere bölebilir veya gruplandırabilir. `CSocket`Sınıf, sizin için paketleme ve paketten açma işlemesi yapılır.

Akışlar açık bağlantılara dayalıdır: A soket, B yuvasına bağlantı ister; B yuvası bağlantı isteğini kabul eder veya reddeder.

Telefon araması, bir akış için iyi bir benzerleme vurguladı sağlar. Normal koşullarda, alıcı taraf, yineleme veya kayıp olmadan söylediklerinizi söyleyebileceğiniz sırada söyler. Akış yuvaları, örneğin, isteğe bağlı olarak ASCII veya ikili dosyaları aktarmayı kolaylaştıran Dosya Aktarım Protokolü (FTP) gibi uygulamalar için uygundur.

Veri boyutu büyük olduğunda akış yuvaları, verilerin gelmesi garantisi olması durumunda veri birimi yuvaları için tercih edilir. Akış yuvaları hakkında daha fazla bilgi için bkz. Windows Yuvaları belirtimi. Belirtim Windows SDK kullanılabilir.

Stream Sockets kullanımı, ağ üzerindeki tüm alma yuvaları yayınlamak için bir veri birimi yuvası kullanmak üzere tasarlanan uygulamalara üst olabilir, çünkü

- Yayın modeli ağ taşma (veya "fırtınası") sorunlarına tabidir.

- Daha sonra benimseyen istemci-sunucu modeli daha etkilidir.

- Akış modeli, veri birimi modelinin olmadığı güvenilir veri aktarımı sağlar.

- Son model, CArchive sınıfı CSocket sınıfına kadar olan Unicode ve ANSI soket uygulamaları arasında iletişim kurma özelliğinden yararlanır.

    > [!NOTE]
    >  Sınıfı kullanırsanız `CSocket` , bir akış kullanmanız gerekir. Yuva türünü **sock_dgram** olarak belirtirseniz mfc onaylama işlemi başarısız olur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)
