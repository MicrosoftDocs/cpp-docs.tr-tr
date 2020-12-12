---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: arka plan'
title: 'Windows Yuvaları: Arka Plan'
ms.date: 11/04/2016
helpviewer_keywords:
- record-oriented data [MFC]
- e-mail [MFC]
- Internet Protocol Suite
- mail [MFC]
- communications [MFC], domain
- Windows Sockets [MFC], stream sockets
- mail [MFC], programming for
- sockets [MFC], stream sockets
- datagram sockets [MFC]
- SOCKET handle
- data types [MFC], socket
- e-mail [MFC], programming for
- X Window servers
- sequenced data flow
- stream sockets [MFC]
ms.assetid: f60d4ed2-bf23-4a0e-98d2-fee77e8473dd
ms.openlocfilehash: 9ac373f5f81dfe3914664d14122a7a6bd46cda40
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214474"
---
# <a name="windows-sockets-background"></a>Windows Yuvaları: Arka Plan

Bu makalede, Windows Sockets 'in doğası ve amacı açıklanmaktadır. Makale ayrıca:

- ["Yuva" terimini tanımlar](#_core_definition_of_a_socket).

- [Yuva tanıtıcı veri türünü açıklar](#_core_the_socket_data_type).

- [Yuvalar için kullanımları açıklar](#_core_uses_for_sockets).

Windows Yuvaları belirtimi, Microsoft Windows için ikili uyumlu bir ağ programlama arabirimi tanımlar. Windows yuvaları, Berkeley 'de University of California 'dan Berkeley yazılım dağıtımı 'nda (BSD, sürüm 4,3) UNIX yuvaları uygulamasını temel alır. Belirtim hem BSD stili yuva yordamlarını hem de Windows 'a özgü uzantıları içerir. Windows Sockets kullanılması, uygulamanızın Windows Sockets API 'sine uyan herhangi bir ağ üzerinde iletişim kurmasına izin verir. Win32 'de, Windows Yuvaları iş parçacığı güvenliği sağlar.

Birçok ağ yazılım satıcısı, Iletim Denetim Protokolü/Internet Protokolü (TCP/IP), Xerox ağ sistemi (XNS), dijital ekipman Corporation 'ın DECNet protokol, Novell Corporation 'ın Internet paket Exchange/sıralı paketlenmiş değişim (IPX/SPX) ve diğer diğer ağ protokolleri altında Windows Yuvaları 'nı destekler. Mevcut Windows Yuvaları belirtimi TCP/IP için yuva soyutlama tanımlar, ancak herhangi bir ağ protokolü, Windows Yuvaları uygulayan dinamik bağlantı kitaplığının (DLL) kendi sürümünü sağlayarak Windows yuvaları ile uyumlu olabilir. Windows yuvaları ile yazılan ticari uygulamalara örnek olarak X Windows Server, Terminal öykünücüleri ve elektronik posta sistemleri dahildir.

> [!NOTE]
> Windows Sockets 'in amacı, bu ağ hakkında bilgi sahibi olmak zorunda kalmaması ve bu sayede uygulamanızın yuvaları destekleyen herhangi bir ağda çalıştırılabilmesi için temel ağı soyutlamak olacaktır. Sonuç olarak, bu belge ağ protokollerinin ayrıntılarını ele almaz.

Microsoft Foundation Class Kitaplığı (MFC), iki sınıf sağlayarak Windows Sockets API 'SI ile programlamayı destekler. Bu sınıflardan biri olan, `CSocket` ağ iletişimleri programlamasını basitleştirmek için yüksek düzeyde soyutlama sağlar.

Windows Yuvaları belirtimi, Windows Yuvaları: Şu anda 1,1 sürümünde, Microsoft Windows altında Ağ Bilgi Işlem için açık bir arabirim, TCP/IP topluluğundaki büyük bireyler ve şirketler grubu tarafından açık bir ağ standardı olarak geliştirilmiştir ve ücretsiz kullanıma sunulmuştur. Yuva programlama modeli, şu anda Internet Protokolü paketini kullanan bir "iletişim etki alanını" destekler. Belirtim Windows SDK kullanılabilir.

> [!TIP]
> Yuvalar Internet Protokolü paketi kullandığından, "Information Highway" üzerinde Internet iletişimlerini destekleyen uygulamalar için tercih edilen yoldur.

## <a name="definition-of-a-socket"></a><a name="_core_definition_of_a_socket"></a> Bir yuvanın tanımı

Yuva, bir Windows Sockets uygulamasının bir ağ üzerinden veri paketleri gönderdiği veya aldığı bir nesne olan bir iletişim uç noktasıdır. Yuva bir türe sahiptir ve çalışan bir işlemle ilişkilendirilir ve bir ada sahip olabilir. Şu anda, Yuvalar genellikle, Internet Protokolü paketini kullanan aynı "iletişim etki alanındaki" diğer yuvalarla yalnızca diğer yuvalarla birlikte Exchange verilerini değiş tokuş ediyor.

Her iki yuva türü çift yönlüdür; Her iki yönde de aynı anda iletilebilecekleri veri akışlardır (tam çift yönlü).

İki yuva türü mevcuttur:

- Akış yuvaları

   Akış yuvaları, kayıt sınırları olmadan bir veri akışı sağlar: bir bayt akışı. Akışların teslim edilmesi ve doğru sıralanmaması ve yinelenmemesi sağlanır.

- Veri birimi yuvaları

   Veri birimi yuvaları, teslim edilmesi garanti edilmeyen, kayda dayalı bir veri akışını destekler ve gönderilmiş veya yinelenmediği olarak sıralanmayabilir.

"Sıralı", paketlerin gönderildiği sırada teslim edildiği anlamına gelir. "Yinelenmeyen", belirli bir paketi yalnızca bir kez almanızı gösterir.

> [!NOTE]
> XNS gibi bazı ağ protokollerinde, akışlar, kayıt yönelimli olarak, bayt akışları yerine kayıt akışları olabilir. Ancak, daha yaygın TCP/IP Protokolü altında akışlar bayt akışlardır. Windows yuvaları, temel Protokolden bağımsız bir soyutlama düzeyi sağlar.

Bu türler ve hangi koşullarda kullanılacak yuva türü hakkında bilgi için bkz. [Windows Yuvaları: akış yuvaları](../mfc/windows-sockets-stream-sockets.md) ve [Windows Yuvaları: veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md).

## <a name="the-socket-data-type"></a><a name="_core_the_socket_data_type"></a> YUVA veri türü

Her MFC yuva nesnesi bir Windows Sockets nesnesine yönelik bir tanıtıcıyı kapsüller. Bu tanıtıcının veri türü **yuva**. **Yuva** tutamacı `HWND` bir pencere için benzerdir. MFC yuva sınıfları, kapsüllenmiş tanıtıcı üzerinde işlemler sağlar.

**Yuva** veri türü Windows SDK ayrıntılı olarak açıklanmıştır. Windows Yuvaları altında "yuva veri türü ve hata değerleri" başlığına bakın.

## <a name="uses-for-sockets"></a><a name="_core_uses_for_sockets"></a> Yuvalar için kullanımlar

Yuvalar, en az üç iletişim bağlamlarında çok yararlı olur:

- İstemci/sunucu modelleri.

- Mesajlaşma uygulamaları gibi eşler arası senaryolar.

- Alıcı uygulamanın bir iletiyi bir işlev çağrısı olarak yorumlamasını sağlayarak uzak yordam çağrıları (RPC) yapma.

> [!TIP]
> MFC yuvalarını kullanmaya yönelik ideal durum, iletişimin iki ucunu yazarken, her iki uçta da MFC 'yi kullanmaktır. Bu konu hakkında daha fazla bilgi için, MFC olmayan uygulamalarla iletişim kurarken durumu yönetme de dahil olmak üzere, bkz. [Windows Yuvaları: bayt sıralaması](../mfc/windows-sockets-byte-ordering.md).

Daha fazla bilgi için bkz. Windows Yuvaları belirtimi: **ntohs**, **ntohl**, **hton**, **htonl**. Ayrıca, aşağıdaki konulara bakın:

- [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: arşivleri kullanan yuvalara örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
