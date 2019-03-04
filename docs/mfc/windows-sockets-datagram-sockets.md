---
title: 'Windows Yuvaları: Veri birimi yuvaları'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 14d33ece66d902b5705e573e9863ea78fff9737f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57266802"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Yuvaları: Veri birimi yuvaları

Bu makalede, veri birimi yuvaları iki Windows yuva türlerinden birini açıklar. (Diğer tür [stream yuva](../mfc/windows-sockets-stream-sockets.md).)

Veri birimi yuvaları sıralı ya da unduplicated garanti edilmez bir çift yönlü veri akışı destekler. Veri birimlerini de güvenilir olmasını garanti edilmez; Bunlar ulaşması başarısız olabilir. Veri birimi veri sıralamaya ve büyük olasılıkla yinelenen gelebilir, ancak kayıtları alıcının iç boyutu sınırdan daha küçük olduğu sürece müşteri verileri kayıt sınırlarındaki korunur. Sıralama ve güvenilirlik yönetmekten sorumlu olursunuz. (Güvenilirlik [LAN] yerel ağlarında iyi olma eğilimindedir ancak daha az vb. geniş alan [WAN] Internet gibi ağlar.)

Veri birimi "bağlantısız", diğer bir deyişle, açık bir bağlantı kurulur. Belirtilen bir yuva için bir veri birimi ileti gönderin ve ileti belirtilen bir yuvadan alma.

Bir veri birimi yuva eşitlenmiş ağ üzerindeki sistem saatlerinin tutan bir uygulama örneğidir. Ek bir özelliği en azından bazı ayarları'nda veri birimi yuvaları, bunu göstermektedir: çok sayıda ağ adresleri yayın iletileri.

Veri birimi yuvaları kayıt odaklı veriler için akış yuvaları iyidir. Veri birimi yuvaları hakkında daha fazla bilgi için bkz: Windows SDK'da bulunan Windows yuva belirtimi.

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows Yuvaları: Arka plan](../mfc/windows-sockets-background.md)
