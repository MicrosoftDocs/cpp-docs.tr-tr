---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: yuva bildirimleri'
title: 'Windows Yuvaları: Yuva Bildirimleri'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], notifications
- notifications [MFC], socket
- sockets [MFC], notifications
ms.assetid: 87d5bf70-6e77-49a9-9a64-aaadee2ad018
ms.openlocfilehash: 856e954050753545a7ff64d3e111c648dc0284d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207663"
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

Sınıfından türetirsiniz `CAsyncSocket` , uygulamanız için ilgilendiğiniz bu ağ olaylarının bildirim işlevlerini geçersiz kılmanız gerekir. Sınıfından bir sınıf türetirsiniz `CSocket` , ilgilendiğiniz bildirim işlevlerinin geçersiz kılınıp kılınmayacağı tercih edilir. Kendisini de kullanabilirsiniz; `CSocket` Bu durumda bildirim varsayılan olarak hiçbir şey yapmaz.

Bu işlevler geçersiz kılınabilir geri arama işlevleridir. `CAsyncSocket` ve `CSocket` iletileri bildirimlere dönüştürebilirsiniz, ancak bunları kullanmak istiyorsanız bildirim işlevlerinin nasıl yanıt vereceğini uygulamalısınız. Bildirim işlevleri, yuvalarınızın, okunacak verilerin varlığı gibi bir olayla ilgili olarak bildirilmesi sırasında çağrılır.

MFC, bildirim işlevlerini çağrı yaptığı sırada, yuvalarınızın davranışını özelleştirmenize olanak tanır. Örneğin, `Receive` bildirim işlevinizden çağrı yapabilirsiniz, `OnReceive` yani okunacak veriler olduğunu bildirmekte, `Receive` onu okumak için çağrın. Bu yaklaşım gerekli değildir, ancak geçerli bir senaryodur. Alternatif olarak, ilerleme durumunu izlemek, **izleme** iletilerini yazdırmak vb. için bildirim işlevinizi kullanabilirsiniz.

Türetilmiş bir yuva sınıfındaki bildirim işlevlerini geçersiz kılarak ve bir uygulama sağlayarak bu bildirimlerin avantajlarından yararlanabilirsiniz.

Veri alma veya gönderme gibi bir işlem sırasında bir `CSocket` nesne zaman uyumlu hale gelir. Zaman uyumlu durum sırasında, diğer yuvaları için geçerli olan tüm bildirimler, geçerli yuva istediği bildirime göre beklerken sıraya alınır. (Örneğin, bir çağrı sırasında `Receive` yuva okumak için bir bildirim ister.) Yuva zaman uyumlu işlemini tamamlayıp zaman uyumsuz hale geldiğinde, diğer yuvalar sıraya alınan bildirimleri almaya başlayabilir.

> [!NOTE]
> `CSocket`' De, `OnConnect` bildirim işlevi hiçbir şekilde çağrılmaz. Bağlantılar için, `Connect` Bağlantı tamamlandığında (başarılı veya hatalı) geri dönecektir. Bağlantı bildirimlerinin nasıl işlendiği, MFC Uygulama ayrıntısıyla belirlenir.

Her bildirim işleviyle ilgili ayrıntılar için `CAsyncSocket` *MFC başvurusu* içindeki sınıf ' ın altındaki işleve bakın. Kaynak kodu ve MFC örnekleri hakkında bilgi için bkz. [MFC örnekleri](../overview/visual-cpp-samples.md#mfc-samples).

Daha fazla bilgi için bkz:

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)

- [Windows Yuvaları: yuvalar, arşivleri ile nasıl çalışır?](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
