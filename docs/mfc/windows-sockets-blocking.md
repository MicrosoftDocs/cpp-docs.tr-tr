---
title: 'Windows Yuvaları: Engelleme'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 26a361bc63da5f6e75144cc91fe837498a7f656b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371970"
---
# <a name="windows-sockets-blocking"></a>Windows Yuvaları: Engelleme

Bu makale ve iki Yardımcısı makaleler Windows Sockets programlamada çeşitli sorunlar açıklanmaktadır. Bu makale, engelleme kapsar. Diğer sorunlar makalelerde ele alınmıştır: [Windows Yuvaları: Bayt sıralama](../mfc/windows-sockets-byte-ordering.md) ve [Windows Yuvaları: Dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).

Kullanıyorsanız veya sınıfından türetilir [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md), bu sorunları kendiniz yönetmeniz gerekecek. Kullanıyorsanız veya sınıfından türetilir [CSocket](../mfc/reference/csocket-class.md), MFC yönetir bunlar sizin için.

## <a name="blocking"></a>Engelleme

Bir yuva "engelleme modu" veya "sayıda modu." olabilir. Kendi işlem tamamlanana kadar engelleme (veya zaman uyumlu) modunda yuva işlevlerini gitmez. Bu, işlev çağrıldı yuva şey yapamazsınız çünkü engelleme adlandırılır — engellenir — çağrı dönene kadar. Bir çağrı `Receive` üye işlevi, örneğin, gönderen uygulamayı göndermek için bekleyeceği gibi tamamlamak için bir rasgele uzun sürebilir (Bu kullanıyorsanız, `CSocket`, veya bu adı kullanıyor `CAsyncSocket` engelleme ile). Varsa bir `CAsyncSocket` nesne çağrısı hemen döndürür (zaman uyumsuz olarak çalışan), sayıda modunda olduğundan ve geçerli hata kodu ile alınabilir [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) bir üye işlevidir **WSAEWOULDBLOCK**, çağrı engellediğiniz gösteren, vardı, hemen modu nedeniyle döndürülmez. (`CSocket` hiç dönmüyor **WSAEWOULDBLOCK**. Sınıfı sizin için engelleme yönetir.)

Yuva davranışını 32-bit ve 64-bit işletim sistemlerinde (örneğin, Windows 95 ya da Windows 98) 16-bit işletim sistemleri (örneğin, Windows 3.1) altında farklıdır. 16-bit işletim sistemlerinde aksine 32-bit ve 64-bit işletim sistemleri, preemptive çok görevli kullanın ve çoklu iş parçacığı kullanımı sağlar. 32 bit ve 64-bit işletim sistemlerinde ayrı iş parçacığı, yuva koyabilirsiniz. Bir iş parçacığında bir yuva işlem süresi engellemesini harcama olmadan ve uygulamanızdaki diğer etkinliklerle engellemesini engelleyebilirsiniz. Çok iş parçacıklı programlama hakkında daha fazla bilgi için bkz [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

> [!NOTE]
>  Çok iş parçacıklı uygulamalarda engelleme yapısını kullanabilirsiniz `CSocket` programınızın tasarım kullanıcı arabiriminin yanıt verme hızını etkilemeden basitleştirmek için. Ana iş parçacığında Kullanıcı etkileşimlerine işleme tarafından ve `CSocket` diğer iş parçacıkları işleme, bu mantıksal işlemleri ayırabilirsiniz. Çok iş parçacıklı olmayan bir uygulamada, bu iki etkinliği birleştirilmiş ve gerekir genellikle kullanılması anlamına gelir bir tek iş parçacığı `CAsyncSocket` isteğe bağlı veya geçersiz kılma iletişim isteklerini işleyebilmesi `CSocket::OnMessagePending` kullanıcı eylemlerini işlemek için uzun zaman uyumlu etkinliği.

Bu tartışma kalan 16-bit işletim sistemlerini hedefleyen programcıları içindir:

Normalde, kullanıyorsanız `CAsyncSocket`, engelleyen işlemler kullanmaktan kaçının ve bunun yerine zaman uyumsuz olarak çalışır. Başlangıçtan aldığınız noktasından zaman uyumsuz işlemler bir **WSAEWOULDBLOCK** hata kodunu arama sonra `Receive`, örneğin kadar bekleyin, `OnReceive` üye işlevi, okuyabilirsiniz bildirmek için çağrılır yeniden. Zaman uyumsuz çağrıları geri, yuva uygun geri çağırma bildirimi işlevi gibi çağıran yapılan [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).

Windows altında engelleme çağrı hatalı bir uygulama olarak kabul edilir. Varsayılan olarak, [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md) destekleyen zaman uyumsuz çağrıları ve yönetmelidir geri bildirimleri kullanarak kendiniz engelleme. Sınıf [CSocket](../mfc/reference/csocket-class.md), diğer taraftan, zaman uyumludur. Windows iletilerini pompalara ve sizin için engelleme yönetir.

Engelleme hakkında daha fazla bilgi için Windows yuva belirtimi bakın. "On" işlevler daha fazla bilgi için bkz. [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md) ve [Windows Yuvaları: Yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md).

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: CAsyncSocket Sınıfını Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)
