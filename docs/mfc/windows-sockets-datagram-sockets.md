---
title: 'Windows Yuvaları: Veri birimi yuvaları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30ad7cab43301ae2cb7ebcb1fb4dfa850090955d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383948"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Yuvaları: Veri Birimi Yuvaları
Bu makalede, veri birimi yuvaları, iki Windows yuva türlerinden birini açıklar. (Diğer tür [akışa yuva](../mfc/windows-sockets-stream-sockets.md).)  
  
 Veri birimi yuvaları sıralı veya unduplicated garanti edilmemiştir bir iki yönlü veri akışı destekler. Veri birimleri de güvenilir olması garanti edilmez; gelmesi başarısız. Veri birimi verisi bozuk ve büyük olasılıkla yinelenen gelebilir, ancak kayıtları alıcının iç boyutu sınırdan daha küçük olduğu sürece müşteri verilerini kayıt sınırlarında korunur. Sıralama ve güvenilirlik yönetmekle sorumlu. (Güvenilirlik [LAN] yerel ağlarda iyi olma eğilimindedir ancak Internet gibi [WAN] daha az vb. geniş alan ağları.)  
  
 Veri birimleri "bağlantısız", diğer bir deyişle, açık bir bağlantı oluşturulur; Belirtilen yuva için bir veri birimi iletisi gönderin ve belirtilen bir yuvadan ileti alabilir.  
  
 Bir veri birimi yuva örneği eşitlenen ağda sistem saatlerinin tutan bir uygulamadır. Bu ek bir veri birimi yuvaları en az bazı ayarları'nda yeteneğini gösterir: çok sayıda ağ adreslerini yayını iletileri.  
  
 Veri birimi yuvaları kayıt odaklı veriler için akış yuvaları iyidir. Veri birimi yuvaları hakkında daha fazla bilgi için bkz: Windows SDK'da bulunan Windows Sockets belirtimi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)   
 [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

