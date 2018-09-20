---
title: 'Windows Yuvaları: Yuva sınıflarından türetme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from socket classes
- Windows Sockets [MFC], deriving from socket classes
- sockets [MFC], deriving from socket classes
ms.assetid: 3a26e67a-e323-433b-9b05-eca018799801
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c562a8d6bf1c3f00f3812f6c25a4afd70276c64f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418963"
---
# <a name="windows-sockets-deriving-from-socket-classes"></a>Windows Yuvaları: Yuva Sınıflarından Türetme

Bu makalede kendi sınıf bir yuva sınıflarından türetme tarafından elde edebilir işlevsellik açıklanır.

Kendi yuva sınıflarından herhangi birinden türetebilirsiniz [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md) veya [CSocket](../mfc/reference/csocket-class.md) kendi işlevselliği eklemek için. Özellikle, çok sayıda kılabileceğiniz sanal üye işlev bu sınıfları sağlar. Bu işlevler dahil [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive), [OnSend](../mfc/reference/casyncsocket-class.md#onsend), [OnAccept](../mfc/reference/casyncsocket-class.md#onaccept), [tetiklediğinde çalıştırılan](../mfc/reference/casyncsocket-class.md#onconnect), ve [OnClose](../mfc/reference/casyncsocket-class.md#onclose). İşlevleri ağ olaylar meydana geldiğinde sağladıkları bildirimleri yararlanmak için türetilmiş yuva sınıfınızda geçersiz kılabilirsiniz. Framework, giriş verilerinin gibi önemli yuva olayları okumaya başlayabilirsiniz bildirmek için bu bildirimi geri çağırma işlevleri çağırır. Bildirim işlevler hakkında daha fazla bilgi için bkz. [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).

Buna ek olarak, sınıf `CSocket` sağlayan [OnMessagePending](../mfc/reference/csocket-class.md#onmessagepending) üye işlevi (Gelişmiş bir geçersiz kılınabilir). Yuva, Windows tabanlı iletileri Pompalama sırada MFC bu işlevi çağırır. Geçersiz kılabilirsiniz `OnMessagePending` Windows belirli iletileri arama ve onlara yanıt vermek için.

Varsayılan sürümü `OnMessagePending` sınıfında sağlanan `CSocket` mesaj kuyruğu WM_PAINT iletileri için bir engelleme çağrısının tamamlanması beklenirken inceler. Bu görüntü kalitesini artırmak için boyama iletileri gönderir. Yararlı bir şeyi yapmanın yanı sıra, bu işlev geçersiz kılabilir bir yolu kendiniz gösterilmektedir. Başka bir örnek olarak kullanmayı `OnMessagePending` aşağıdaki görev. Bir ağ işlemin tamamlanması beklenirken modsuz iletişim kutusu görüntüler varsayalım. İletişim kutusu, kullanıcının çok uzun süren durdurma işlemi iptal etmek için kullanabileceğiniz bir iptal düğmesi içerir. `OnMessagePending` Geçersiz kılma için bu modsuz iletişim kutusu ilgili iletiler pompa.

İçinde `OnMessagePending` geçersiz, ya da dönüş **TRUE** veya temel sınıf sürümü bir çağrıdan dönüş `OnMessagePending`. Yine de istediğiniz işlerini gerçekleştirir, temel sınıf sürümü çağırın.

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)

- [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)

- [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

