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
ms.openlocfilehash: 87d4f0eb57f9e26dbf73da06b5d7ca6d61d6c174
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81359992"
---
# <a name="windows-sockets-blocking"></a>Windows Yuvaları: Engelleme

Bu makale ve iki yardımcı makale, Windows Soketleri programlamaçeşitli sorunları açıklar. Bu makalede engelleme kapsar. Diğer konular makalelerde ele alınmıştır: [Windows Soketleri: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md) ve [Windows Soketleri: Dizeleri dönüştürme.](../mfc/windows-sockets-converting-strings.md)

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfı kullanıyor veya bu türlerden türetilmiştir, bu sorunları kendiniz yönetmeniz gerekir. [CSocket](../mfc/reference/csocket-class.md)sınıfı kullanıyor veya bu sınıftan türetilmiştir, MFC bunları sizin için yönetir.

## <a name="blocking"></a>Engelleme

Bir soket "engelleme modunda" veya "engelleme modunda" olabilir. Engelleme (veya senkron) modundaki soketlerin işlevleri, eylemlerini tamamlayana kadar geri dönmez. İşlevi çağrılan soket hiçbir şey yapamadığı için bu engelleme olarak adlandırılır — çağrı dönene kadar engellenir. Örneğin, üye `Receive` işlevine yapılan bir çağrının, gönderen uygulamanın gönderilmesini beklediği için tamamlanması rasgele uzun zaman alabilir `CSocket`(bu, kullanıyorsanız veya engelleme yle kullanıyorsanız). `CAsyncSocket` Bir `CAsyncSocket` nesne engelleme modundaysa (eş zamanlı olarak çalışıyorsa), çağrı hemen döner ve [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) üye işlevi ile alınabilir olan geçerli hata kodu **WSAEWOULDBLOCK'dur**, mod nedeniyle hemen döndürülmeseydi çağrının engellendiğini gösterir. (`CSocket` **wsaewouldblock**asla . Sınıf sizin için engelleme yönetir.)

Soketlerin davranışları 32 bit ve 64 bit işletim sistemleri (Windows 95 veya Windows 98 gibi) altında 16 bit işletim sistemlerinin (Windows 3.1 gibi) altında farklıdır. 16 bit işletim sistemlerinin aksine, 32-bit ve 64-bit işletim sistemleri preemptive çoklu görev kullanır ve çoklu iş parçacığı sağlar. 32 bit ve 64 bit işletim sistemleri altında soketlerinizi ayrı çalışma iş parçacıklarına yerleştirebilirsiniz. İş parçacığındaki bir soket, uygulamanızdaki diğer etkinliklere müdahale etmeden ve engellemede işlem zamanı harcamadan engelleyebilir. Çok iş parçacığı programlama hakkında bilgi için, [multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md)makalesine bakın.

> [!NOTE]
> Çok iş parçacıklı uygulamalarda, kullanıcı arabiriminin `CSocket` yanıt verme yeteneğini etkilemeden programınızın tasarımını basitleştirmek için engelleme yapısını kullanabilirsiniz. Ana iş parçacığındaki kullanıcı etkileşimlerini işleyerek ve `CSocket` alternatif iş parçacıklarında işleyerek, bu mantıksal işlemleri ayırabilirsiniz. Çok iş parçacığı olmayan bir uygulamada, bu iki etkinlik birleştirilmeli ve tek bir `CAsyncSocket` iş parçacığı olarak ele alınmalıdır, `CSocket::OnMessagePending` bu da genellikle isteğe bağlı iletişim isteklerini işlemek için kullanmak veya uzun eşzamanlı etkinlik sırasında kullanıcı eylemlerini işlemek için geçersiz kılınması anlamına gelir.

Bu tartışmanın geri kalanı 16 bit işletim sistemlerini hedefleyen programcılar içindir:

Normalde, kullanıyorsanız, `CAsyncSocket`engelleme işlemleri kullanmaktan kaçınmalı ve bunun yerine eşzamanlı olarak çalışmalısınız. Eşzamanlı işlemlerde, bir **WSAEWOULDBLOCK** hata kodunu aldıktan sonra `Receive`,örneğin, üye işlevinizin `OnReceive` çağrılmasını bekleyin ve yeniden okuyabileceğinizi bildirirsiniz. Eşkron aramalar, soketinizin [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive)gibi uygun geri arama bildirim işlevini geri çağırarak yapılır.

Windows'un altında, aramaları engelleme kötü uygulama olarak kabul edilir. Varsayılan olarak, [CAsyncSocket](../mfc/reference/casyncsocket-class.md) eşzamanlı çağrıları destekler ve geri arama bildirimlerini kullanarak engellemeyi yönetmeniz gerekir. Sınıf [CSocket](../mfc/reference/csocket-class.md), diğer taraftan, senkron. Windows iletilerini pompalar ve sizin için engelleme yönetir.

Engelleme hakkında daha fazla bilgi için Windows Soketleri belirtimine bakın. "Açık" işlevleri hakkında daha fazla bilgi için [Windows Soketleri: Soket Bildirimleri](../mfc/windows-sockets-socket-notifications.md) ve [Windows Soketleri: Soket Sınıflarından Türeyen.](../mfc/windows-sockets-deriving-from-socket-classes.md)

Daha fazla bilgi için bkz.

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket::OnSend](../mfc/reference/casyncsocket-class.md#onsend)
