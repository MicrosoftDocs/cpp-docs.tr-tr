---
title: "Windows Yuvaları: Bağlantı noktaları ve yuva adresleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 768ccdc197df8d38cb594c2408bb6fc6998dfdcb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri
Bu makalede koşulları "port" ve "Windows Yuvaları ile kullanılan adresi" olarak açıklanmaktadır.  
  
##  <a name="_core_port"></a>Bağlantı noktası  
 Bir bağlantı noktası, bir hizmet sağlanabilir benzersiz bir işlemi tanımlar. Mevcut bağlamda Windows Sockets destekleyen bir uygulama ile ilişkili bir bağlantı noktasıdır. Böylece, aynı anda bir makine üzerinde çalışan birden fazla Windows Sockets uygulama her Windows Sockets uygulama benzersiz şekilde tanımlamak için kullanılan uygulamadır.  
  
 Belirli bağlantı noktalarını, FTP gibi ortak Hizmetleri için ayrılmıştır. Bu tür bir hizmeti sağlayan sürece bu bağlantı noktalarını kullanarak kaçınmalısınız. Windows Yuvaları belirtimi bu ayrılmış bağlantı noktaları ayrıntılarını verir. WINSOCK dosya. H bunları listeler.  
  
 Windows Yuvaları kullanılabilir bir bağlantı noktası seçtiğiniz DLL izin vermek için 0 bağlantı noktası değeri geçirin. MFC 1.024 ondalık büyük bir bağlantı noktası değeri seçer. MFC çağırarak seçilen bağlantı noktası değeri alabilir [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) üye işlevi.  
  
##  <a name="_core_socket_address"></a>Yuva adresi  
 Her yuva nesnesi ağ üzerinde bir Internet Protokolü (IP) adresi ile ilişkilidir. Genellikle, "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi bir noktalı sayı adresidir.  
  
 Bir yuva oluşturmak aradığınızda, genellikle kendi adresini belirtmek gerekmez.  
  
> [!NOTE]
>  Makinenizde birden çok ağ kartları (veya uygulamanızın gün böyle bir makinede çalıştırın,), mümkünse her farklı bir ağ temsil eden. Bu durumda, yuva kullanacağı hangi ağ kartı belirtmek için bir adres sağlamak gerekebilir. Gelişmiş kullanım ve olası taşınabilirlik sorunu belirli budur.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Yuvaların arşivlerle çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Yuvaları: Akış yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

