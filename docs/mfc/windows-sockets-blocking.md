---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: engelleme'
title: 'Windows Yuvaları: Engelleme'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], blocking mode
- Windows Sockets [MFC], Windows platforms
- Windows Sockets [MFC], blocking mode
- sockets [MFC], behavior on different Windows platforms
- blocking mode sockets
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
ms.openlocfilehash: 21d1a2fb635f3d45e639c950a7ad1748dc3dda74
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197458"
---
# <a name="windows-sockets-blocking"></a>Windows Yuvaları: Engelleme

Bu makalede ve iki yardımcı makalede Windows Sockets programlamasında çeşitli sorunlar açıklanmaktadır. Bu makalede engelleme ele alınmaktadır. Şu makalelerde diğer sorunlar ele alınmıştır: [Windows Yuvaları: bayt sıralaması](../mfc/windows-sockets-byte-ordering.md) ve [Windows Yuvaları: dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md).

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfından kullanırsanız veya türetirsiniz, bu sorunları kendiniz yönetmeniz gerekecektir. [CSocket](../mfc/reference/csocket-class.md)sınıfından kullanırsanız veya türetirsiniz, MFC bunları sizin için yönetir.

## <a name="blocking"></a>Engelleme

Yuva, "engelleme modu" veya "engellenmeyen mod" içinde olabilir. Engelleme (veya zaman uyumlu) modundaki yuvaların işlevleri, eylemlerini tamamlayabilecekleri sürece döndürmez. Bu, işlevi çağrılan bir yuva hiçbir şey yapamadığı için engelleme olarak adlandırılır; çağrı dönene kadar engellenir. `Receive`Örneğin, üye işlevine yapılan bir çağrı, gönderen uygulamanın gönderilmesini beklediği için oldukça uzun zaman alabilir (Bu, kullanıyorsanız `CSocket` veya `CAsyncSocket` engelleme ile kullanıyorsanız). Bir `CAsyncSocket` nesne engellenmeyen bir moddadır (zaman uyumsuz), çağrı hemen döndürülür ve [GetLastError](../mfc/reference/casyncsocket-class.md#getlasterror) üye işleviyle birlikte gelen geçerli hata kodu, bu çağrının, mod nedeniyle hemen döndürülmeyeceğini belirten **wsaewouldblock**' dir. ( `CSocket` hiçbir şekilde **wsaewouldblock** döndürmez. Sınıfı, engellemeyi sizin için yönetir.)

Yuvalar davranışı, 16 bit işletim sistemleri (örneğin, Windows 3,1) altında 32-bit ve 64 bit işletim sistemlerinde (Windows 95 veya Windows 98 gibi) farklıdır. 16 bit işletim sistemlerinden farklı olarak, 32-bit ve 64 bit işletim sistemleri preemptive çok görevli kullanır ve çoklu iş parçacıklı sağlar. 32-bit ve 64-bit işletim sistemleri altında, yuvalarınızı ayrı çalışan iş parçacıklarıyla birlikte yerleştirebilirsiniz. İş parçacığı içindeki bir yuva, uygulamanızdaki diğer etkinlikleri etkilemeden ve engellemede işlem süresi harcamadan engelleyebilirler. Çoklu iş parçacıklı programlama hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

> [!NOTE]
> Çok iş parçacıklı uygulamalarda, `CSocket` Kullanıcı arabiriminin yanıt hızını etkilemeden programınızın tasarımını basitleştirmek için engelleme yapısını kullanabilirsiniz. Ana iş parçacığında kullanıcı etkileşimini ve `CSocket` diğer iş parçacıklarında işlemeyi işleyerek, bu mantıksal işlemleri ayırabilirsiniz. Çok iş parçacıklı olmayan bir uygulamada, bu iki etkinliğin tek bir iş parçacığı olarak birleştirilmesi ve işlenmesi gerekir. Bu, genellikle, `CAsyncSocket` isteğe bağlı iletişim isteklerini işleyebilmeniz veya `CSocket::OnMessagePending` uzun zaman uyumlu etkinlik sırasında kullanıcı eylemlerini işlemek için geçersiz kılmasıdır.

Bu tartışmanın geri kalanı 16 bit işletim sistemlerini hedefleyen programcılar içindir:

Genellikle, kullanıyorsanız `CAsyncSocket` , engelleyici işlemleri kullanmaktan kaçının ve bunun yerine zaman uyumsuz olarak işlem yapmanız gerekir. Zaman uyumsuz işlemlerde, çağrıldıktan sonra bir **wsaewouldblock** hata kodu aldığınız noktadan `Receive` , örneğin, `OnReceive` tekrar okuyabilmeniz için üye işleviniz çağrılana kadar bekler. Zaman uyumsuz çağrılar, yuvanın uygun geri çağırma bildirimi işlevinizi geri arayarak yapılır, örneğin [OnReceive](../mfc/reference/casyncsocket-class.md#onreceive).

Windows altında, engelleme çağrıları kötü uygulama olarak kabul edilir. Varsayılan olarak, [CAsyncSocket](../mfc/reference/casyncsocket-class.md) zaman uyumsuz çağrıları destekler ve geri arama bildirimleri kullanarak engellemeyi kendiniz yönetmeniz gerekir. Diğer yandan sınıf [CSocket](../mfc/reference/csocket-class.md), zaman uyumludur. Windows iletileri üflemeli ve engellemeyi sizin için yönetir.

Engelleme hakkında daha fazla bilgi için bkz. Windows Yuvaları belirtimi. "On" işlevleri hakkında daha fazla bilgi için bkz. [Windows Yuvaları: yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md) ve [Windows Yuvaları: yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md).

Daha fazla bilgi için bkz:

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)<br/>
[CAsyncSocket:: OnSend](../mfc/reference/casyncsocket-class.md#onsend)
