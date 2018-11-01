---
title: 'Windows Yuvaları: Veri Birimi Yuvaları'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 886409d4072a77244cff415c6f0a6a3f533e42d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462133"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Yuvaları: Veri Birimi Yuvaları

Bu makalede, veri birimi yuvaları iki Windows yuva türlerinden birini açıklar. (Diğer tür [stream yuva](../mfc/windows-sockets-stream-sockets.md).)

Veri birimi yuvaları sıralı ya da unduplicated garanti edilmez bir çift yönlü veri akışı destekler. Veri birimlerini de güvenilir olmasını garanti edilmez; Bunlar ulaşması başarısız olabilir. Veri birimi veri sıralamaya ve büyük olasılıkla yinelenen gelebilir, ancak kayıtları alıcının iç boyutu sınırdan daha küçük olduğu sürece müşteri verileri kayıt sınırlarındaki korunur. Sıralama ve güvenilirlik yönetmekten sorumlu olursunuz. (Güvenilirlik [LAN] yerel ağlarında iyi olma eğilimindedir ancak daha az vb. geniş alan [WAN] Internet gibi ağlar.)

Veri birimi "bağlantısız", diğer bir deyişle, açık bir bağlantı kurulur. Belirtilen bir yuva için bir veri birimi ileti gönderin ve ileti belirtilen bir yuvadan alma.

Bir veri birimi yuva eşitlenmiş ağ üzerindeki sistem saatlerinin tutan bir uygulama örneğidir. Ek bir özelliği en azından bazı ayarları'nda veri birimi yuvaları, bunu göstermektedir: çok sayıda ağ adresleri yayın iletileri.

Veri birimi yuvaları kayıt odaklı veriler için akış yuvaları iyidir. Veri birimi yuvaları hakkında daha fazla bilgi için bkz: Windows SDK'da bulunan Windows yuva belirtimi.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

