---
title: 'Windows Yuvaları: Yuva bildirimleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c6fd065d13d3c61b88cc24144cfc64368020d16
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953977"
---
# <a name="windows-sockets-socket-notifications"></a>Windows Yuvaları: Yuva Bildirimleri
Bu makalede yuva sınıflardaki bildirim işlevleri açıklanmaktadır. Bu üye işlevleri yuva nesnenizin önemli olayları bildirmek için framework çağıran geri çağırma işlevlerdir. Bildirim işlevler şunlardır:  
  
-   [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): olduğunu veri arabelleği çağırarak almak de bu yuva bildirir [alma](../mfc/reference/casyncsocket-class.md#receive).  
  
-   [OnSend](../mfc/reference/casyncsocket-class.md#onsend): Bu yuva şimdi veri çağırarak gönderebilmesi gerektiğini bildirir [Gönder](../mfc/reference/casyncsocket-class.md#send).  
  
-   [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): Bekleyen bağlantı istekleri çağırarak alabilen bu dinleme yuva bildirir [kabul](../mfc/reference/casyncsocket-class.md#accept).  
  
-   [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): bağlantı denemesi tamamlandı bu yuva bağlantı bildirir: belki de başarıyla ya da belki hatası.  
  
-   [OnClose](../mfc/reference/casyncsocket-class.md#onclose): bağlı için yuva kapattı bu yuva bildirir.  
  
    > [!NOTE]
    >  Bir ek bildirim işlevi [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata). Bu bildirim alıcı yuva gönderen yuva göndermek için "bant-" verilerin olduğunu bildirir. Bant dışı verileri, her bağlı Akış yuvaları çifti ile ilişkili mantıksal olarak bağımsızdır bir kanaldır. Bant dışı kanal genellikle "Acil" veri göndermek için kullanılır. MFC bant dışı verileri destekler. Sınıfıyla çalışan kullanıcılar Gelişmiş [CAsyncSocket](../mfc/reference/casyncsocket-class.md) bant dışı kanal, ancak kullanıcılar sınıfının kullanmanız gerekebilir [CSocket](../mfc/reference/csocket-class.md) kullanmasını önerilmez. En kolay yolu, bu tür veri geçirme için ikinci bir yuva oluşturmaktır. Bant dışı verileri hakkında daha fazla bilgi için bkz: Windows SDK'da bulunan Windows Sockets belirtimi.  
  
 Sınıfından türetirseniz `CAsyncSocket`, uygulamanıza olaylarının bu ağ için bildirim işlevleri geçersiz kılmanız gerekir. Sınıfından bir sınıf türetirseniz `CSocket`, ilgi bildirim işlevleri geçersiz kılınıp kılınmayacağını sizin tercihinize bağlıdır. Aynı zamanda `CSocket` kendisini; bu durumda bildirim işlevleri hiçbir şey yapmak için varsayılan.  
  
 Geçersiz kılınabilir geri arama işlevleri bu işlevlerdir. `CAsyncSocket` ve `CSocket` dönüştürme iletileri bildirimleri, ancak bunları kullanmak istiyorsanız, bildirim yanıt nasıl çalıştığını uygulamalıdır. Bildirim İşlevler, yuva ilgi okumak için veri gibi bir olay bildirim zaman çağrılır.  
  
 MFC yuva ait davranışı haberdar aynı anda özelleştirmenize olanak bildirim işlevlerini çağırır. Örneğin, çağırabilirsiniz `Receive` gelen, `OnReceive` bildirim işlevi, diğer bir deyişle, olmaya bildirim verileri okumak için çağırmanız `Receive` okumak için. Bu yaklaşım gerekli değildir, ancak geçerli bir senaryodur. Alternatif olarak, ilerleme durumunu izlemek için bildirim işlevi kullanabilir yazdırma **izleme** iletileri ve benzeri.  
  
 Bu bildirimler türetilmiş yuva sınıfında bildirim işlevleri geçersiz kılma ve bir uygulama sağlama yararlanabilirsiniz.  
  
 Teslim alma veya veri gönderen gibi bir işlem sırasında bir `CSocket` nesne zaman uyumlu olur. Geçerli yuva istediği bildirim için beklerken zaman uyumlu durum sırasında diğer yuva için amacı herhangi bir bildirim kuyruğa alınır. (Örneğin, sırasında bir `Receive` çağrısı, yuva istediği okumak için bir bildirim.) Yuva zaman uyumlu işlemi tamamlandıktan ve yeniden zaman uyumsuz haline geldikten sonra diğer yuva sıraya alınan bildirimleri almaya başlayabilirsiniz.  
  
> [!NOTE]
>  İçinde `CSocket`, `OnConnect` bildirim işlevi hiçbir zaman çağrılır. Bağlantılar için arama `Connect`, hangi döndürecektir bağlantı (başarıyla veya hata) tamamlandığında. Bağlantı bildirimleri işlenme bir MFC uygulaması ayrıntı olur.  
  
 Sınıf altında işlevi her bildirim işlevi hakkında daha fazla bilgi için bkz `CAsyncSocket` içinde *MFC başvurusu*. Kaynak kodu ve MFC örnekleri hakkında bilgi için bkz: [MFC örnekleri](../visual-cpp-samples.md).  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

