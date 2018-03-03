---
title: "Windows Yuvaları: Akış yuvaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bc112bd3cfbf1194a2898afecb513edcbc456747
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-stream-sockets"></a>Windows Yuvaları: Akış Yuvaları
Bu makalede akış yuvaları, iki Windows yuva türlerinden birini açıklar. (Diğer tür [veri birimi yuva](../mfc/windows-sockets-datagram-sockets.md).)  
  
 Akış yuvaları sağlamak kayıt sınırlar olmadan bir veri akışı için: çift yönlü olabilir bayt akışı (tam çift yönlü uygulamasıdır: Bu hem iletebilir ve yuva alırsınız). Akışlar temel sıralı, unduplicated verileri sunmak için dayanıyordu. ("Sıralı" paketleri gönderilen sırayla teslim edilmesini anlamına gelir. "Unduplicated", belirli bir paket yalnızca bir kez elde anlamına gelir.) Giriş akışı iletilerinin garanti ve akışlar büyük miktarlarda veri işleme için uygundur.  
  
 Ağ aktarım katmanı bölmek veya makul boyutunun paketlere veri grubu olabilir. `CSocket` Sınıfı paketleme ve sizin için paketi açılırken işleyecek.  
  
 Akışlar, açık bağlantıları dayalı: Yuva A B; yuva bağlantı istekleri Yuva B kabul veya bağlantı isteği reddeder.  
  
 Telefon görüşmesi için bir akış iyi benzerleme sağlar. Normal koşullar altında çoğaltma veya kaybı söylenebilir, sırayla söyleyin alıcı taraf duyar. Akış yuvaları, örneğin, uygulamaları gibi Dosya Aktarım Protokolü (hangi dosya aktarımı ASCII veya ikili dosyalar rasgele boyutunun kolaylaştıran FTP), için uygundur.  
  
 Akış yuvaları gelmesi veri garanti gerekir ve veri boyutu büyük olduğunda veri birimi yuvaları için tercih edilir. Akış yuvaları hakkında daha fazla bilgi için Windows Sockets belirtime bakın. Belirtimi, Windows SDK'ın kullanılabilir.  
  
 Akış yuvaları kullanarak çünkü yayınlamak için ağdaki tüm alıcı yuva için bir veri birimi yuva kullanmak üzere tasarlanmış uygulamalara üstün olabilir  
  
-   Yayın ağ sel (veya "storm") sorunları tabi modelidir.  
  
-   Daha sonra benimsenen istemci-sunucu modeli daha verimli olur.  
  
-   Akış modeli burada veri birimi model yok güvenilir veri aktarımı sağlar.  
  
-   Son model CArchive CSocket sınıfı için uygundur o sınıfın yuva uygulamaları ANSI ve Unicode arasında iletişim kurma becerisini yararlanır.  
  
    > [!NOTE]
    >  Sınıfı kullanırsanız `CSocket`, bir akış kullanmanız gerekir. Yuva türü olarak belirtirseniz bir MFC onaylama başarısız **SOCK_DGRAM**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)   
 [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

