---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: veri birimi Yuvaları'
title: 'Windows Yuvaları: Veri Birimi Yuvaları'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 8de374d6e96348504d4b1fc126c1607c029cd6c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132983"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Yuvaları: Veri Birimi Yuvaları

Bu makalede, kullanılabilir iki Windows yuva türünden biri olan veri birimi yuvaları açıklanmaktadır. (Diğer tür [Stream soketi](../mfc/windows-sockets-stream-sockets.md)olur.)

Veri birimi yuvaları, sıralı veya yinelenenleri kaldırma garantisi olmayan çift yönlü bir veri akışını destekler. Ayrıca, veri birimlerinin güvenilir olması garanti edilmez; Bunlar ulaşamazlar. Veri birimi verileri sıra dışına çıkabilir ve muhtemelen yinelenebilir, ancak kayıtlar alıcının iç boyut sınırından daha küçük olduğu sürece verilerdeki kayıt sınırları korunur. Sıralamayı ve güvenilirliği yönetmekten siz sorumlusunuz. (Güvenilirlik, yerel ağlarda [LAN], ancak Internet gibi geniş ağlarda (WAN) daha düşük bir şekilde olabilir.)

Veri birimleri "bağlantısız", diğer bir deyişle açık bağlantı kurulmaz; Belirtilen bir yuvaya bir veri birimi iletisi gönderir ve belirtilen bir yuvadan iletiler alabilirsiniz.

Veri birimi yuvasına örnek olarak, ağdaki sistem saatlerinin eşitlenmiş durumda kalmasını sağlayan bir uygulamadır. Bu, en az bazı ayarlarda çok sayıda veri birimi yuvalarının ek bir özelliğini gösterir: çok sayıda ağ adresine ileti yayınlama.

Veri birimi yuvaları, kayda dayalı veriler için akış yuvalara göre daha iyidir. Veri birimi yuvaları hakkında daha fazla bilgi için, Windows SDK bulunan Windows Yuvaları belirtimine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)
