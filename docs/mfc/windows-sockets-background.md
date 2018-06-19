---
title: 'Windows Yuvaları: Arka plan | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fda86bbbeb49bcb253348ed02abef4fb8d4cff9c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384943"
---
# <a name="windows-sockets-background"></a>Windows Yuvaları: Arka Plan
Bu makalede yapısı ve Windows Yuvaları amacı açıklanmaktadır. Makale ayrıca:  
  
-   ["Yuva" terimi tanımlar](#_core_definition_of_a_socket).  
  
-   [SOCKET tanıtıcısı veri türünü tanımlar](#_core_the_socket_data_type).  
  
-   [Yuva kullanımları açıklar](#_core_uses_for_sockets).  
  
 Windows Yuvaları belirtimi Microsoft Windows için bir ikili uyumlu ağ arabirimi tanımlar. Windows Yuvaları Berkeley yazılım dağıtımı UNIX yuva uygulamasında temel alır (BSD, 4.3 sürüm) Berkeley'deki University of California gelen. Belirtimi BSD stili yuva yordamları ve Windows'a özgü uzantılar içerir. Windows Yuvaları kullanarak uygulamanız için Windows Sockets API uyan herhangi bir ağ üzerinden iletişim kurmasına izin verir. Win32'Windows yuvaları için iş parçacığı güvenliği sağlar.  
  
 Birçok ağ yazılım satıcısı İletim Denetimi Protokolü/Internet Protokolü (TCP/IP), Xerox ağ sistem (XNS), dijital ekipman Corporation'ın DECNet protokolü, Novell Corporation'ın Internet dahil olmak üzere ağ protokolleri altında Windows Sockets desteği Paket Değişimi/Sıralı paketlenmiş Değişimi (IPX/SPX) ve diğerleri. TCP/IP'yi yuva soyutlama mevcut Windows Sockets belirtimi tanımlamasına rağmen bir ağ protokolü kendi Windows Sockets uygulayan dinamik bağlantı kitaplığı (DLL) sürümünü sağlayarak Windows Yuvaları ile uyumlu. Windows Yuvaları ile yazılmış ticari uygulamaların örnekleri X Windows sunucuları, terminal Öykünücüler ve elektronik posta sistemleri içerir.  
  
> [!NOTE]
>  Windows Yuvaları amacı, bu ağ hakkında bilgi sahibi olmak zorunda değildir ve uygulamanızı yuva destekleyen herhangi bir ağda çalıştırabilmeniz için temel alınan ağ hemen soyut olmaktır. Sonuç olarak, bu belge ağ protokolleri ayrıntılarını açıklanmamıştır.  
  
 Microsoft Foundation Class Kitaplığı (MFC), iki sınıf sağlayarak Windows Sockets API ile programlama destekler. Bu sınıfların birini `CSocket`, yüksek düzeyde bir ağ iletişimi programlama basitleştirmek için Özet sağlar.  
  
 Windows Yuvaları belirtimi, Windows Yuvaları: bir açmak arabirimi ağ bilgi işlem altında Microsoft Windows için artık sürüm 1.1, en çok sayıda kişiler ve TCP/IP'yi topluluğundaki şirketler tarafından açık bir ağ standart geliştirilmiştir ve olduğu ücretsiz olarak kullanılabilir. Modelini destekleyen bir "iletişimi etki alanı" şu anda programlama, Internet Protokolü paketi kullanarak yuva. Belirtimi, Windows SDK'ın kullanılabilir.  
  
> [!TIP]
>  Yuva Internet Protokolü paketi kullandığından "bilgi Otoyol." Internet iletişimini destekleyen uygulamalar için tercih edilen yol oldukları  
  
##  <a name="_core_definition_of_a_socket"></a> Bir yuva tanımı  
 Bir yuva bir iletişim uç noktası olan — bir nesne içinden, bir Windows Sockets uygulaması gönderir veya bir ağ üzerinden veri paketleri alır. Bir yuva türüne sahip ve çalışan bir işlemle ilişkili ve bir ad olabilir. Şu anda, yuva genellikle yalnızca diğer yuva "Internet Protokolü paketi kullanan aynı iletişimi etki alanında," ile veri değişimi.  
  
 Her iki tür yuva çift yönlü; yine de uygun istiyor musunuz? Her iki yönde de aynı anda bildirilmesi veri akışları oldukları (tam çift yönlü).  
  
 İki yuva türleri kullanılabilir:  
  
-   Akış yuvaları  
  
     Akış yuvaları kayıt sınırlar olmadan veri akışı için sağlar: bir akış bayt. Akışları teslim edilecek doğru sıralı ve unduplicated garanti.  
  
-   Veri birimi yuvaları  
  
     Teslim edilecek kesin değildir ve olarak sıralı değil veri birimi yuvaları destek kayıt odaklı veri akışı gönderilen veya unduplicated.  
  
 "Sıralı" paketleri gönderilen sırayla teslim edilmesini anlamına gelir. "Unduplicated" belirli bir paket yalnızca bir kez elde anlamına gelir.  
  
> [!NOTE]
>  XNS gibi bazı ağ protokolleri altında akışları bayt akışları yerine kayıtları akışları olarak yönelik kayıt olabilir. Daha yaygın TCP/IP protokolü altında ancak bayt akışları akışlarıdır. Windows Yuvaları temel protokolünden bağımsız özet düzeyi sağlar.  
  
 Bu türleri hakkında bilgi için ve hangi durumlarda kullanmak için bkz: Yuva hangi tür [Windows Yuvaları: akış yuvaları](../mfc/windows-sockets-stream-sockets.md) ve [Windows Yuvaları: veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md).  
  
##  <a name="_core_the_socket_data_type"></a> YUVA veri türü  
 Her MFC yuva nesnesi Windows Sockets nesnesi için bir tanıtıcı yalıtır. Veri türü bu tanıtıcının **YUVA**. A **YUVA** işleyicisidir benzer `HWND` bir pencere için. MFC yuva sınıflarından kapsüllenmiş tanıtıcı işlemler sağlar.  
  
 **YUVA** veri türü Windows SDK ayrıntılı açıklanmıştır. Windows Yuvaları altında "Yuva veri türü ve hata değerlerini" bakın.  
  
##  <a name="_core_uses_for_sockets"></a> Yuva için de kullanır  
 Yuva en az üç iletişimleri bağlamlarda çok yararlı olur:  
  
-   İstemci/sunucu modeli.  
  
-   İleti gönderme uygulamaları gibi eşler arası senaryolar.  
  
-   Uzaktan yordam çağrısı (RPC), bir iletiyi bir işlev çağrısı olarak yorumlamak alma işlemini yapan uygulamanın sağlayarak yapılıyor.  
  
> [!TIP]
>  Her iki ucuna iletişimin yazılırken MFC yuva kullanmak için ideal bir durumdur: her iki uçta MFC kullanma. MFC dışı uygulamalarla kurarken durum yönetme de dahil olmak üzere, bu konu hakkında daha fazla bilgi için bkz: [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md).  
  
 Windows Yuvaları belirtimi daha fazla bilgi için bkz: **ntohs**, **ntohl**, **htons**, **htonl**. Ayrıca, aşağıdaki konulara bakın:  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

