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
ms.openlocfilehash: 6ab866609d0b75aaf9d06a01c204433d80e7e3d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62217884"
---
# <a name="windows-sockets-background"></a>Windows Yuvaları: Arka Plan

Bu makalede, doğası ve Windows Sockets amacını açıklar. Makale ayrıca:

- ["Yuva" terimi tanımlar](#_core_definition_of_a_socket).

- [SOCKET tanıtıcısı veri türünü açıklayan](#_core_the_socket_data_type).

- [Yuva kullanımları açıklar](#_core_uses_for_sockets).

Windows Yuvaları belirtimi Microsoft Windows için bir ikili ile uyumlu ağ arabirimi tanımlar. Windows Yuvaları Berkeley yazılım dağıtımı UNIX yuva uygulamasında temel (BSD, 4.3 sürüm) California Üniversitesi, Berkeley öğesinden. Belirtimi BSD stili yuva yordamları ve Windows için belirli uzantılar içerir. Windows Yuvaları kullanma, uygulamanızı Windows Sockets API'si için uygun olan herhangi bir ağ üzerinden iletişim kurmasına izin verir. Win32'de, Windows Sockets için iş parçacığı güvenliği sağlar.

Birçok ağ yazılım satıcısı Windows Sockets altında İletim Denetimi Protokolü/Internet Protokolü (TCP/IP), Xerox ağ sistem (XNS) Digital Equipment Corporation'ın DECNet protokolü, Novell Corporation'ın İnternet'e dahil olmak üzere ağ protokolleri destekler. Paket Exchange/sıralı paketlenmiş Değişimi (IPX/SPX) ve diğerleri. Mevcut Windows yuva belirtimi için TCP/IP yuva soyutlama tanımlasa da herhangi bir ağ protokolünü uygulayan Windows Sockets dinamik bağlantı kitaplığı (DLL) kendi sürümüne sağlanarak Windows Sockets ile uyumlu. Windows Sockets ile yazılmış ticari uygulamaların X Windows sunucuları, terminal öykünücüsünü ve elektronik posta sistemleri verilebilir.

> [!NOTE]
>  Windows Yuvaları amacı, temel ağ, ağ hakkında bilgi sahibi olmak zorunda değildir ve uygulamanızı yuva destekleyen herhangi bir ağda çalışabilmesi hemen soyut sağlamaktır. Sonuç olarak, bu belge ağ protokolleri ayrıntılarını ele almaz.

Microsoft Foundation Class Kitaplığı'nı (MFC), iki sınıf sağlanarak Windows Sockets API'si ile programlama destekler. Bu sınıflardan birine `CSocket`, yüksek düzeyde soyutlama, ağ iletişimi programlama basitleştirmek için sağlar.

Windows Yuvaları belirtimi, Windows Yuvaları: Açık arabirim ağ bilgi işlem altında Microsoft Windows, artık sürüm 1.1, en çok sayıda kişiler ve TCP/IP'yi topluluğundaki şirketler tarafından açık bir ağ standart geliştirilmiştir ve kullanılmak üzere özgürce kullanılabilir. Yuva modelini destekleyen bir "iletişimi etki alanı" şu anda programlama, Internet Protokolü paketi kullanma. Belirtimi Windows SDK içinde kullanılabilir.

> [!TIP]
>  Yuva Internet Protokolü paketi kullandığından, "bilgi Otoyol." Internet iletişimini destekleyen uygulamalar için tercih edilen yol oldukları.

##  <a name="_core_definition_of_a_socket"></a> Bir yuva tanımı

Bir iletişim uç noktası yuvası olup — bir nesne üzerinden Windows Sockets uygulama gönderir veya bir ağ üzerinden veri paketlerini alır. Bir yuva bir türe sahiptir ve çalışan bir işleme ile ilişkilendirilir ve bir ad olabilir. Şu anda, yuva genellikle yalnızca "Internet Protokolü paketi kullanan aynı iletişim etki alanında," diğer yuvaları ile veri değişimi.

Çift yönlü yuva her iki çeşidi değildir; oldukları her iki yönde de aynı anda bildirilmesi bir veri akışı (tam çift yönlü).

İki yuva türleri kullanılabilir:

- Stream yuva

   Stream yuva sağlamak için bir veri akışı kayıt sınırlar olmadan: bayt akışı. Akışları teslim edilecek ve doğru şekilde sıralı inceleyip unduplicated garanti edilir.

- Veri birimi yuvaları

   Teslim garanti edilmez ve olarak sıralı değil veri birimi yuvaları destek kayıt odaklı veri akışı gönderilen veya unduplicated.

"Sıralı" paketleri sıraya gönderilen teslim edilmesini anlamına gelir. "Unduplicated" belirli bir paket yalnızca bir kez elde anlamına gelir.

> [!NOTE]
>  XNS gibi bazı ağ protokolleri altında akışları bayt akışlarında yerine kayıt akışları olarak yönelik kayıt olabilir. Daha yaygın TCP/IP protokolünün altında ancak bayt akışları akışlarıdır. Windows Yuvaları temel alınan protokolünden bağımsız bir özet düzeyi sağlar.

Bu türleri hakkında daha fazla bilgi ve hangi durumlarda kullanmak üzere yuva hangi tür [Windows Yuvaları: Stream yuva](../mfc/windows-sockets-stream-sockets.md) ve [Windows Yuvaları: Veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md).

##  <a name="_core_the_socket_data_type"></a> YUVA veri türü

Her MFC yuva nesnesi Windows Sockets nesnesi için bir tanıtıcı kapsüller. Bu veri türü **YUVA**. A **YUVA** işleyicisidir alınmak üzere `HWND` pencere. MFC yuva sınıflarından kapsüllenmiş tutamacın üzerinde işlemler sağlar.

**YUVA** veri türü, Windows SDK'sındaki ayrıntılı açıklanmıştır. "Yuva veri türü ve hata değerlerini" Windows Sockets altında görürsünüz.

##  <a name="_core_uses_for_sockets"></a> Yuva kullanımları

Yuva en az üç iletişimleri bağlamlarda oldukça kullanışlıdır:

- İstemci/sunucu modeli.

- Eşler arası senaryoları, Mesajlaşma uygulamaları gibi.

- Uzaktan yordam çağrısı (RPC), bir iletiyi bir işlev çağrısı olarak yorumlamak alıcı uygulamanın sağlayarak yapılıyor.

> [!TIP]
>  Her iki ucunda da iletişim yazarken MFC Yuvaları kullanma için ideal bir durumdur: MFC her iki uçta kullanma. MFC olmayan uygulamalar ile kurarken durum yönetme de dahil olmak üzere, bu konu hakkında daha fazla bilgi için bkz. [Windows Yuvaları: Bayt sıralama](../mfc/windows-sockets-byte-ordering.md).

Daha fazla bilgi için Windows Sockets belirtime bakın: **ntohs**, **ntohl**, **htons**, **htonl**. Ayrıca, aşağıdaki konulara bakın:

- [Windows Yuvaları: Yuvaları Arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Arşivlerle kullanılan yuvalara örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)

- [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
