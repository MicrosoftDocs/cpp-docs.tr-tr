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
ms.openlocfilehash: 791bf07c927e80e65e0fda79fae8a50235bc2def
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371042"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri

Bu makalede, Windows Soketleri ile kullanılan "bağlantı noktası" ve "adres" terimleri açıklanmaktadır.

## <a name="port"></a><a name="_core_port"></a>Bağlantı noktası

Bağlantı noktası, bir hizmetin sağlanabileceği benzersiz bir işlemi tanımlar. Bu bağlamda, bir bağlantı noktası Windows Soketleri destekleyen bir uygulama ile ilişkilidir. Amaç, her Windows Soketleri uygulamasını benzersiz bir şekilde tanımlamak, böylece aynı anda bir makinede birden fazla Windows Soketi uygulamasının çalışmasını sağlayabilirsiniz.

FtP gibi ortak hizmetler için belirli bağlantı noktaları ayrılmıştır. Bu tür bir hizmet sağlamadığınız sürece bu bağlantı noktalarını kullanmaktan kaçınmalısınız. Windows Soketleri belirtimi bu ayrılmış bağlantı noktalarını ayrıntılarıyla anlatır. Winsock dosyası. H de onları listeler.

Windows Soketleri DLL'nin sizin için kullanılabilir bir bağlantı noktası seçmesine izin vermek için bağlantı noktası değeri olarak 0'ı geçirin. MFC, 1.024 ondalık değerinden büyük bir bağlantı noktası değeri seçer. [CAsyncSocket::GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) üye işlevini arayarak MFC'nin seçtiği bağlantı noktası değerini alabilirsiniz.

## <a name="socket-address"></a><a name="_core_socket_address"></a>Soket Adresi

Her soket nesnesi ağdaki bir Internet Protokolü (IP) adresiyle ilişkilidir. Genellikle, adres "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayıdır.

Bir soket oluşturmak istediğinizde, genellikle kendi adresinizi belirtmeniz gerekmez.

> [!NOTE]
> Makinenizin her biri farklı bir ağı temsil eden birden çok ağ kartı (veya uygulamanızın bir gün böyle bir makinede çalışması) olabilir. Bu nedenle, soketin hangi ağ kartını kullanacağını belirtmek için bir adres vermeniz gerekebilir. Bu gelişmiş bir kullanım ve olası bir taşınabilirlik sorunu olduğu kesindir.

Daha fazla bilgi için bkz.

- [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Yuvaların Arşivlerle Çalışması](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
