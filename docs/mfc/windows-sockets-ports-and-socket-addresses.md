---
title: 'Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri'
ms.date: 11/04/2016
helpviewer_keywords:
- ports [MFC], definition
- Windows Sockets [MFC], ports
- Windows Sockets [MFC], addresses
- ports [MFC]
- addresses [MFC], socket
- sockets [MFC], addresses
- sockets [MFC], ports
ms.assetid: e050261a-9285-4f31-a1c5-6c8033af5b4a
ms.openlocfilehash: d132001cb792877e3d476508a6a5bb456dfb5987
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631367"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri

Bu makalede, koşulları "bağlantı noktası" ve "Windows Sockets ile kullanılan adresi" olarak açıklanmaktadır.

##  <a name="_core_port"></a> Bağlantı noktası

Bir bağlantı noktası, bir hizmet sağlanması benzersiz bir işlemi tanımlar. Mevcut bağlamda bir bağlantı noktası Windows Sockets destekleyen bir uygulama ile ilişkilidir. Her Windows Sockets uygulama çalıştıran bir makinede aynı anda birden fazla Windows Sockets uygulama denetlenebilmesi benzersiz şekilde tanımlamak için kullanılan olur.

Belirli bağlantı noktalarını, FTP gibi sık kullanılan hizmetler için ayrılmıştır. Size, bu tür bir hizmet sağlanması sürece bu bağlantı noktalarını kullanarak kaçınmanız gerekir. Windows Yuvaları belirtimi bu ayrılmış bağlantı noktaları ayrıntıları. WINSOCK dosya. H bunları listeler.

Windows Yuvaları kullanılabilir bir bağlantı noktası seçtiğiniz DLL izin vermek için 0 bağlantı noktası değeri geçirin. MFC 1024 ondalık büyük bir bağlantı noktası değeri seçer. MFC çağırarak seçilen bağlantı noktası değeri alabilir [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) üye işlevi.

##  <a name="_core_socket_address"></a> Yuva adresi

Her yuva nesnesi, ağ üzerinde bir Internet Protokolü (IP) adresi ile ilişkilidir. Genellikle, "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı adresidir.

Yuva oluşturma arama yaparken, genellikle kendi adresinizi belirtin gerekmez.

> [!NOTE]
>  Makinenizde birden çok ağ bağdaştırıcısı olan (veya uygulamanızı gün gibi bir makinede çalıştırmak), her farklı bir ağ temsil eden. Bu durumda, hangi ağ kartı yuva kullanacağı belirtmek için bir adres sağlamak gerekebilir. Gelişmiş bir kullanım ve olası taşınabilirlik sorunu belirli budur.

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca Bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

