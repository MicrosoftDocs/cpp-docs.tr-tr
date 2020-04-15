---
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
ms.openlocfilehash: 1c4a6dc6740660d1097785578cdac355983cad18
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360122"
---
# <a name="windows-sockets-background"></a>Windows Yuvaları: Arka Plan

Bu makalede, Windows Soketleri'nin doğası ve amacı açıklanmaktadır. Makale de:

- ["Soket" terimini tanımlar.](#_core_definition_of_a_socket)

- [SOCKET işleişi veri türünü açıklar.](#_core_the_socket_data_type)

- [Soketlerin kullanımlarını açıklar.](#_core_uses_for_sockets)

Windows Soketleri belirtimi, Microsoft Windows için ikili uyumlu ağ programlama arabirimi tanımlar. Windows Soketleri Berkeley California Üniversitesi Berkeley Yazılım Dağıtımı (BSD, sürüm 4.3) UNIX soketleri uygulama dayanmaktadır. Belirtim, hem BSD tarzı soket yordamlarını hem de Windows'a özgü uzantıları içerir. Windows Soketleri'ni kullanmak, uygulamanızın Windows Soketleri API'sine uygun herhangi bir ağ üzerinden iletişim kurmasına izin verir. Win32'de, Windows Soketleri iş parçacığı güvenliğini sağlar.

Birçok ağ yazılımı satıcısı, Iletim Kontrol Protokolü/Internet Protokolü (TCP/IP), Xerox Ağ Sistemi (XNS), Digital Equipment Corporation'ın DECNet protokolü, Novell Corporation'ın Internet Packet Exchange/Sequenced Packed Exchange (IPX/SPX) ve diğerleri dahil olmak üzere ağ protokolleri altında Windows Soketlerini destekler. Mevcut Windows Sockets belirtimi TCP/IP için soketleri soyutlama tanımlasa da, herhangi bir ağ protokolü Windows Soketleri uygulayan dinamik bağlantı kitaplığı (DLL) kendi sürümünü sağlayarak Windows Soketleri ile uyumlu olabilir. Windows Soketleri ile yazılmış ticari uygulamalara örnek olarak X Windows sunucuları, terminal emülatörleri ve elektronik posta sistemleri verilebilir.

> [!NOTE]
> Windows Soketleri'nin amacı, bu ağ hakkında bilgili olmak zorunda kalmamak ve böylece uygulamanızın soketleri destekleyen herhangi bir ağda çalıştırabilmesi için temel ağı soyutlamaktır. Sonuç olarak, bu belgeler ağ protokollerinin ayrıntılarını tartışmaz.

Microsoft Foundation Class Library (MFC), iki sınıf sağlayarak Windows Soketleri API'si ile programlamayı destekler. Bu sınıflardan `CSocket`biri, ağ iletişim programlama basitleştirmek için soyutlama yüksek düzeyde sağlar.

Windows Soketleri belirtimi, Windows Soketleri: Microsoft Windows altında Ağ Bilgi İşlem için Açık Arabirim, şimdi sürüm 1.1, TCP / IP topluluğunda bireyler ve şirketler büyük bir grup tarafından açık ağ standardı olarak geliştirilmiştir ve serbestçe kullanılabilir. Soket programlama modeli, Internet Protocol Suite'i kullanarak şu anda bir "iletişim etki alanını" destekler. Belirtim Windows SDK'da mevcuttur.

> [!TIP]
> Soketler Internet Protocol Suite'i kullandığından, "bilgi otobanında" Internet iletişimini destekleyen uygulamalar için tercih edilen yoldur.

## <a name="definition-of-a-socket"></a><a name="_core_definition_of_a_socket"></a>Sokettanımı

Soket, Windows Sockets uygulamasının ağ üzerinden veri paketleri gönderdiği veya aldığı bir nesne olan bir iletişim bitiş noktasıdır. Bir soketin bir türü vardır ve çalışan bir işlemle ilişkilidir ve bir adı olabilir. Şu anda soketler genellikle internet protokol paketini kullanan aynı "iletişim etki alanında" yalnızca diğer soketlerle veri alışverişi yapmaktadır.

Her iki soket türü de çift yönlü; aynı anda her iki yönde de iletilebilecek veri akışlarıdır (tam çift yönlü).

İki soket türü mevcuttur:

- Akış yuvaları

   Akış soketleri, kayıt sınırları olmayan bir veri akışı sağlar: bir bayt akışı. Akışların teslim edilmesi ve doğru sıralanıp çoğaltılmama garantisi vardır.

- Veri birimi yuvaları

   Datagram soketleri, teslim edilmesi garanti edilmeyen ve gönderilmeveya çoğaltılmamış olarak sıralanamayan kayıt yönelimli bir veri akışını destekler.

"Sıralı", paketlerin gönderilen siparişte teslim olduğu anlamına gelir. "Çoğaltılmadı" belirli bir paketi yalnızca bir kez aldığınız anlamına gelir.

> [!NOTE]
> XNS gibi bazı ağ protokolleri altında, akışlar bayt akışları yerine kayıt akışları olarak kayda yönelik olabilir. Ancak, daha yaygın olan TCP/IP protokolü altında akışlar bayt akışlarıdır. Windows Soketleri, temel protokolden bağımsız bir soyutlama düzeyi sağlar.

Bu tür ve hangi durumlarda hangi soket lerin kullanılacağı hakkında bilgi için [Bkz. Windows Soketleri: Akış Soketi](../mfc/windows-sockets-stream-sockets.md) ve [Windows Soketleri: Datagram Soketleri.](../mfc/windows-sockets-datagram-sockets.md)

## <a name="the-socket-data-type"></a><a name="_core_the_socket_data_type"></a>SOCKET Veri Türü

Her MFC soketi nesnesi bir Windows Soketleri nesnesine bir tutamacı kapsüller. Bu tanıtıcının veri **SOCKET**türü SOCKET'dir. **SOKET** tutamacı, bir `HWND` pencere için benzerdir. MFC soket sınıfları kapsüllü tutamaç üzerinde işlem sağlar.

**SOCKET** veri türü Windows SDK'da ayrıntılı olarak açıklanmıştır. Bkz. Windows Soketleri altında "Soket Veri Türü ve Hata Değerleri"

## <a name="uses-for-sockets"></a><a name="_core_uses_for_sockets"></a>Soketler için kullanım alanları

Soketler en az üç iletişim bağlamında son derece yararlıdır:

- İstemci/sunucu modelleri.

- İleti uygulamaları gibi eşler arası senaryolar.

- Alıcı uygulamanın bir iletiyi işlev çağrısı olarak yorumlatarak uzaktan yordam çağrıları (RPC) yapma.

> [!TIP]
> MFC soketlerini kullanmak için ideal durum, iletişimin her iki ucunu da yazarken: Her iki uçta da MFC kullanmak. MFC dışı uygulamalarla iletişim kurarken servis talebinin nasıl yönetilecek olması da dahil olmak üzere bu konu hakkında daha fazla bilgi için [Windows Soketleri: Bayt Siparişi'](../mfc/windows-sockets-byte-ordering.md)ne bakın.

Daha fazla bilgi için Windows Soketleri Belirtimi: **ntohs**, **ntohl**, **htons**, **htonl**. Ayrıca, aşağıdaki konulara bakın:

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
