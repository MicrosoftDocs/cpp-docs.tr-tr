---
title: 'Windows Yuvaları: Yuva Bildirimleri'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
ms.openlocfilehash: 10dbe6c0e1f486257c50efc4acf917cd9d596630
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80167777"
---
# <a name="windows-sockets-socket-notifications"></a>Windows Yuvaları: Yuva Bildirimleri

Bu makalede, yuva sınıflarında bildirim işlevleri açıklanmaktadır. Bu üye işlevleri, Framework 'ün önemli olaylarınızın yuva nesneniz konusunda çağrı yaptığı geri çağırma işlevleridir. Bildirim işlevleri şunlardır:

- [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive): Bu yuvaya [alma](../mfc/reference/casyncsocket-class.md#receive)çağrısı yaparak alınması için arabellekte veri olduğunu bildirir.

- [OnSend](../mfc/reference/casyncsocket-class.md#onsend): Bu yuvaya şimdi [Gönder](../mfc/reference/casyncsocket-class.md#send)'i çağırarak veri gönderemeyeceğini bildirir.

- [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept): Bu dinleme yuvasına, [kabul etme](../mfc/reference/casyncsocket-class.md#accept)çağrısı yaparak bekleyen bağlantı isteklerini kabul edemeyeceğini bildirir.

- [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect): Bu bağlama yuvasına bağlantı denemesini bildirir: Belki başarıyla veya belki hatalı.

- [OnClose](../mfc/reference/casyncsocket-class.md#onclose): Bu yuvaya bağlı olan yuvanın kapatıldığını bildirir.

    > [!NOTE]
    >  Ek bir bildirim işlevi, [OnOutOfBandData](../mfc/reference/casyncsocket-class.md#onoutofbanddata)' dır. Bu bildirim, alıcı yuvasına gönderme yuvasının "bant dışı" verilerinin gönderilmesini söyler. Bant dışı veriler, her bağlı akış yuvası çiftiyle ilişkili mantıksal olarak bağımsız bir kanaldır. Bant dışı kanal genellikle "acil" verileri göndermek için kullanılır. MFC bant dışı verileri destekler. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) sınıfı ile çalışan ileri düzey kullanıcıların bant dışı kanalı kullanması gerekebilir, ancak [CSocket](../mfc/reference/csocket-class.md) sınıfının kullanıcıları bu uygulamayı kullanmaktan önerilmez. Daha kolay yol, bu tür verileri geçirmek için ikinci bir yuva oluşturmaktır. Bant dışı veriler hakkında daha fazla bilgi için Windows SDK bulunan Windows Yuvaları belirtimine bakın.

`CAsyncSocket`sınıfından türetirsiniz, uygulamanıza ilgilendiğiniz bu ağ olaylarının bildirim işlevlerini geçersiz kılmanız gerekir. `CSocket`sınıfından bir sınıf türetirsiniz, ilgilendiğiniz bildirim işlevlerinin geçersiz kılınıp engellenip engellenmeyeceğini tercih edersiniz. `CSocket` kendisini de kullanabilirsiniz; Bu durumda bildirim varsayılan olarak hiçbir şey yapmaz.

Bu işlevler geçersiz kılınabilir geri arama işlevleridir. `CAsyncSocket` ve `CSocket` iletileri bildirimlere dönüştürür, ancak bunları kullanmak istiyorsanız bildirim işlevlerinin nasıl yanıt vereceğini uygulamalısınız. Bildirim işlevleri, yuvalarınızın, okunacak verilerin varlığı gibi bir olayla ilgili olarak bildirilmesi sırasında çağrılır.

MFC, bildirim işlevlerini çağrı yaptığı sırada, yuvalarınızın davranışını özelleştirmenize olanak tanır. Örneğin, `OnReceive` bildirim işlevinizden `Receive` çağırabilirsiniz, diğer bir deyişle, okunacak veriler olduğu konusunda bilgi almak için `Receive` çağırın. Bu yaklaşım gerekli değildir, ancak geçerli bir senaryodur. Alternatif olarak, ilerleme durumunu izlemek, **izleme** iletilerini yazdırmak vb. için bildirim işlevinizi kullanabilirsiniz.

Türetilmiş bir yuva sınıfındaki bildirim işlevlerini geçersiz kılarak ve bir uygulama sağlayarak bu bildirimlerin avantajlarından yararlanabilirsiniz.

Veri alma veya gönderme gibi bir işlem sırasında, `CSocket` bir nesne zaman uyumlu hale gelir. Zaman uyumlu durum sırasında, diğer yuvaları için geçerli olan tüm bildirimler, geçerli yuva istediği bildirime göre beklerken sıraya alınır. (Örneğin, bir `Receive` çağrısı sırasında yuva okumak için bir bildirim ister.) Yuva zaman uyumlu işlemini tamamlayıp zaman uyumsuz hale geldiğinde, diğer yuvalar sıraya alınan bildirimleri almaya başlayabilir.

> [!NOTE]
> `CSocket`, `OnConnect` bildirim işlevi hiçbir şekilde çağrılmaz. Bağlantılar için, bağlantı tamamlandığında (başarılı veya hatalı) döndürülen `Connect`çağırır. Bağlantı bildirimlerinin nasıl işlendiği, MFC Uygulama ayrıntısıyla belirlenir.

Her bildirim işleviyle ilgili ayrıntılar için *MFC başvurusu*içindeki sınıf `CAsyncSocket` altındaki işleve bakın. Kaynak kodu ve MFC örnekleri hakkında bilgi için bkz. [MFC örnekleri](../overview/visual-cpp-samples.md#mfc-samples).

Daha fazla bilgi için bkz.

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
