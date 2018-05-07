---
title: 'Windows Yuvaları: Bağlantı noktaları ve yuva adresleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42ea9b8a39de8d36ecb621164d98e072a4041211
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri
Bu makalede koşulları "port" ve "Windows Yuvaları ile kullanılan adresi" olarak açıklanmaktadır.  
  
##  <a name="_core_port"></a> Bağlantı noktası  
 Bir bağlantı noktası, bir hizmet sağlanabilir benzersiz bir işlemi tanımlar. Mevcut bağlamda Windows Sockets destekleyen bir uygulama ile ilişkili bir bağlantı noktasıdır. Böylece, aynı anda bir makine üzerinde çalışan birden fazla Windows Sockets uygulama her Windows Sockets uygulama benzersiz şekilde tanımlamak için kullanılan uygulamadır.  
  
 Belirli bağlantı noktalarını, FTP gibi ortak Hizmetleri için ayrılmıştır. Bu tür bir hizmeti sağlayan sürece bu bağlantı noktalarını kullanarak kaçınmalısınız. Windows Yuvaları belirtimi bu ayrılmış bağlantı noktaları ayrıntılarını verir. WINSOCK dosya. H bunları listeler.  
  
 Windows Yuvaları kullanılabilir bir bağlantı noktası seçtiğiniz DLL izin vermek için 0 bağlantı noktası değeri geçirin. MFC 1.024 ondalık büyük bir bağlantı noktası değeri seçer. MFC çağırarak seçilen bağlantı noktası değeri alabilir [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) üye işlevi.  
  
##  <a name="_core_socket_address"></a> Yuva adresi  
 Her yuva nesnesi ağ üzerinde bir Internet Protokolü (IP) adresi ile ilişkilidir. Genellikle, "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi bir noktalı sayı adresidir.  
  
 Bir yuva oluşturmak aradığınızda, genellikle kendi adresini belirtmek gerekmez.  
  
> [!NOTE]
>  Makinenizde birden çok ağ kartları (veya uygulamanızın gün böyle bir makinede çalıştırın,), mümkünse her farklı bir ağ temsil eden. Bu durumda, yuva kullanacağı hangi ağ kartı belirtmek için bir adres sağlamak gerekebilir. Gelişmiş kullanım ve olası taşınabilirlik sorunu belirli budur.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

