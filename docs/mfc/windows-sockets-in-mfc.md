---
title: "MFC'de Windows Yuvaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 01c61a00fe9a0f34a6f1237e0b7307fd8924e6be
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-in-mfc"></a>MFC'de Windows Yuvaları
> [!NOTE]
>  MFC Windows Yuva 1'i destekler ancak desteklemediği [Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673). Windows Yuvaları 2 ilk Windows 98 ile birlikte gelen ve Windows 2000'de bulunan sürümüdür.  
  
 MFC Windows yuvaları, iki MFC sınıfları gerçekleştirilen ile ağ iletişimi programları yazmak için iki modeli sağlar. Bu makalede bu modeller ve daha ayrıntılı bilgi MFC yuva desteği. "Yuva" iletişimin bir uç noktadır: üzerinden uygulamanızı iletişim kuran diğer Windows Sockets uygulamaları ile ağ üzerinden bir nesne.  
  
 Windows yuvaları, yuva kavramı bir açıklaması da dahil olmak üzere hakkında bilgi için bkz: [Windows Yuvaları: arka plan](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a>Programlama modelleri yuvaları  
 İki MFC Windows programlama modelleri yuvaları aşağıdaki sınıflar tarafından desteklenir:  
  
-   `CAsyncSocket`  
  
     Bu sınıf Windows Sockets API yalıtır. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) kimin ağ programlama bilmeniz ve programlama doğrudan API yuva için esneklik istiyorsanız ancak aynı zamanda geri arama işlevleri kolaylık ağ olayları bildirim için istediğiniz programcıları için geçerlidir. C++ kullanmak için nesne yönelimli formunda yuva paketleme dışında bu sınıfın sağladığı yalnızca ek Özet belirli yuva ilgili Windows iletilerini geri aramalar dönüştürülüyor. Daha fazla bilgi için bkz: [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md).  
  
-   `CSocket`  
  
     Bu sınıf türetilen `CAsyncSocket`, yuva bir MFC ile çalışmak için daha yüksek bir düzeyinde Özet sağlayan [CArchive](../mfc/reference/carchive-class.md) nesnesi. Bir yuva büyük ölçüde ile ilgili bir arşiv kullanarak MFC'nin dosya serileştirme protokolü kullanarak benzer. Bu, daha kolaylaştırır `CAsyncSocket` modeli. [CSocket](../mfc/reference/csocket-class.md) çok sayıda üye işlevleri devralır `CAsyncSocket` Windows Sockets API'leri kapsülleyen; bu işlevler bazıları kullanın ve genellikle programlama yuva anlama sahip olacaktır. Ancak `CSocket` ham API veya sınıfı kullanarak kendiniz yapmak zorunda iletişimi pek çok görünüşünün yönetir `CAsyncSocket`. En önemlisi, `CSocket` (arka plan Windows iletilerinin işlenmesini ile), engelleme sağlar eşzamanlı bir işlem gerekli olduğu `CArchive`.  
  
 Oluşturma ve kullanma `CSocket` ve `CAsyncSocket` nesneleri açıklanan [Windows Yuvaları: arşivlerle kullanılan yuvalara](../mfc/windows-sockets-using-sockets-with-archives.md) ve [Windows Yuvaları: sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md).  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>Windows Yuvaları: DLL'leri  
 Microsoft Windows işletim sistemleri Windows Sockets dinamik bağlantı kitaplığı (DLL) sağlayın. Visual C++ uygun üstbilgi dosyaları ve kitaplıkları ve Windows Yuvaları belirtimi sağlar.  
  
> [!NOTE]
>  16 bit uygulamalar için Windows Sockets desteği, Windows NT ve Windows 2000 altında WINSOCK üzerinde temel alır. DLL. 32-bit uygulamaları için desteği WSOCK32 içinde değil. DLL. 32 bit devam parametreleri 32-bit sürümlerde dışında sağlanan API'leri aynıdır. Win32 altında iş parçacığı güvenliği sağlanır.  
  
 Windows Yuvaları hakkında daha fazla bilgi için bkz:  
  
-   [Windows Yuvaları: Akış yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: İşlem dizisi](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Windows Yuvaları: Arşivlerle kullanılan yuvalara örnek](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows Yuvaları: Yuvaların arşivlerle çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuva sınıflarından türetme](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Yuvaları: Yuva bildirimleri](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Yuvaları: Bayt sıralama](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Yuvaları: Dizeleri dönüştürme](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows Yuvaları: Bağlantı noktaları ve yuva adresleri](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Windows Yuvaları](../mfc/windows-sockets.md)

