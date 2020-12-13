---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: yuva sınıflarından türetme'
title: 'Windows Yuvaları: Yuva Sınıflarından Türetme'
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
ms.openlocfilehash: ba3526ddde4d254ff044fa09588d7764b16fb719
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132970"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Yuvaları: Yuva Sınıflarından Türetme

Bu makalede, soket sınıflarından birindeki kendi sınıfınızı türeterek elde edebileceğinizi bazı işlevler açıklanmaktadır.

Kendi işlevlerinden birini eklemek için, [CAsyncSocket](../mfc/reference/casyncsocket-class.md) veya [CSocket](../mfc/reference/csocket-class.md) ' den kendi yuva sınıflarınızı türetebilirsiniz. Özellikle, bu sınıflar geçersiz kılabileceğiniz bir dizi sanal üye işlevlerini sağlar. Bu işlevler [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [OnConnect](../mfc/reference/casyncsocket-class.md#onconnect)ve [OnClose](../mfc/reference/casyncsocket-class.md#onclose)içerir. Ağ olayları gerçekleştiğinde sağladığı bildirimlerin avantajlarından yararlanmak için, türetilmiş yuva sınıfınıza ait işlevleri geçersiz kılabilirsiniz. Framework, okumaya başlayabileceğiniz verilerin alınması gibi önemli yuva olaylarını size bildirmek için bu bildirim geri çağırma işlevlerini çağırır. Bildirim işlevleri hakkında daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).

Ayrıca, sınıfı `CSocket` [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) üye işlevini sağlar (Gelişmiş geçersiz kılınabilir). Yuva Windows tabanlı iletileri pompalarken MFC bu işlevi çağırır. `OnMessagePending`Windows 'dan belirli iletileri aramak ve bunlara yanıt vermek için geçersiz kılabilirsiniz.

Sınıfında sağlanan varsayılan sürümü, `OnMessagePending` `CSocket` bir engelleme çağrısının tamamlanmasını beklerken WM_PAINT iletileri için ileti kuyruğunu inceler. Görüntü kalitesini artırmak için Paint iletileri gönderir. Faydalı bir şey yapmanın yanı sıra, işlevi kendiniz geçersiz kılabileceğiniz bir yolu gösterir. Başka bir örnek olarak, `OnMessagePending` Aşağıdaki görev için kullanmayı düşünün. Ağ işleminin tamamlanmasını beklerken kalıcı olmayan bir iletişim kutusu görüntülediğinizi varsayın. İletişim kutusu, kullanıcının çok uzun süren işlemleri engellemeyi iptal etmek için kullanabileceği bir Iptal düğmesi içerir. `OnMessagePending`Geçersiz kılma, bu engelleyici olmayan iletişim kutusuyla ilgili ileti göndericileri gösterebilir.

`OnMessagePending`Geçersiz kılmada, **doğru** ya da temel sınıf sürümüne yapılan çağrıdan geri döndürün `OnMessagePending` . Yine de istediğiniz işi gerçekleştiriyorsa, temel sınıf sürümünü çağırın.

Daha fazla bilgi için bkz:

- [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
