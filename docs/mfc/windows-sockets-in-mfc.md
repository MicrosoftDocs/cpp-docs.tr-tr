---
title: MFC'de Windows Yuvaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8b497fc7e5e22a654d1f5037a983165fcd5594c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194987"
---
# <a name="windows-sockets-in-mfc"></a>MFC'de Windows Yuvaları
> [!NOTE]
>  MFC Windows Yuva 1'i destekler ancak desteklemediği [Windows Sockets 2](/windows/desktop/WinSock/windows-sockets-start-page-2). Windows Sockets 2 ilk sevk Windows 98 ve Windows 2000'de bulunan sürümüdür.  
  
 MFC, iki MFC sınıfları düzenlenen Windows Sockets ile ağ iletişimi programları yazmak için iki modeli sağlar. Bu makalede bu modeller ve daha ayrıntılı bilgi MFC yuva desteği. "Yuva" olan bir uç nokta iletişim: üzerinden uygulamanızı iletişim kuran diğer Windows Sockets uygulamaları ile bir ağ üzerinden bir nesne.  
  
 Yuva kavram, bir açıklama da dahil olmak üzere Windows Sockets hakkında bilgi için bkz. [Windows Yuvaları: arka plan](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a> Yuva programlama modelleri  
 MFC Windows programlama modellerini iki yuva aşağıdaki sınıflar tarafından desteklenir:  
  
-   `CAsyncSocket`  
  
     Bu sınıf Windows Sockets API'SİNİN kapsüller. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) olduğu programcılara ağ programlama bilmeniz ve programlama sockets API'si için doğrudan'ın esnekliği istiyoruz, ancak Ayrıca ağ olay bildirimi için geri çağırma işlevleri kolaylık istiyor. Yuva kullanılmak üzere C++ nesne yönelimli formunda paketleme dışında bu sınıfın sağladığı yalnızca ek Özet belirli yuva ilgili Windows iletilerini geri çağırmaları dönüştürüyor. Daha fazla bilgi için [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).  
  
-   `CSocket`  
  
     Bu sınıf, türetilen `CAsyncSocket`, yuva aracılığıyla bir MFC ile çalışmak için daha yüksek bir düzeyinde Özet sağlayan [CArchive](../mfc/reference/carchive-class.md) nesne. Bir yuva büyük ölçüde ile bir arşiv kullanarak MFC'nin dosya serileştirme protokolü kullanarak benzer. Bu sayede daha kolay daha `CAsyncSocket` modeli. [CSocket](../mfc/reference/csocket-class.md) birçok üye işlevleri devralan `CAsyncSocket` Windows Sockets API'leri kapsülleyen; bu işlevler bazılarını kullanmak ve yuva programlamasında genellikle anlamak gerekir. Ancak `CSocket` ham API veya sınıfı kullanarak kendiniz yapmak zorunda iletişim birçok yönüyle yönetir `CAsyncSocket`. En önemlisi, `CSocket` sağlar (arka plan Windows iletilerinin işlenmesini ile), engelleyici eşzamanlı işlemi için gerekli olan `CArchive`.  
  
 Oluşturma ve kullanma `CSocket` ve `CAsyncSocket` nesneleri açıklanan [Windows Yuvaları: yuvaların arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md) ve [Windows Yuvaları: sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md).  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Yuvaları: DLL'leri  
 Microsoft Windows işletim sistemleri, Windows Sockets dinamik bağlantı kitaplıklarını (DLL) sağlayın. Visual C++, uygun bir başlık dosyaları ve kitaplıkları ve Windows yuva belirtimi sağlar.  
  
 Windows Yuvaları hakkında daha fazla bilgi için bkz:  
  
-   [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: İşlem Dizisi](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Windows Yuvaları: Arşivlerle Kullanılan Yuvalara Örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuva Sınıflarından Türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Yuvaları: Yuva Bildirimleri](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Yuvaları: Bayt Sıralama](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Yuvaları: Dizeleri Dönüştürme](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Yuvaları](../mfc/windows-sockets.md)

