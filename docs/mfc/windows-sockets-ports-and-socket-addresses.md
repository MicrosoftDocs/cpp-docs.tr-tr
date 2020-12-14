---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: bağlantı noktaları ve yuva adresleri'
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
ms.openlocfilehash: 354505796ff60cc8968b2e10a2aac98be2eb4666
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263406"
---
# <a name="windows-sockets-ports-and-socket-addresses"></a>Windows Yuvaları: Bağlantı Noktaları ve Yuva Adresleri

Bu makalede, Windows yuvaları ile kullanılan "bağlantı noktası" ve "adres" terimleri açıklanmaktadır.

## <a name="port"></a><a name="_core_port"></a> Bağ

Bir bağlantı noktası, bir hizmetin sağlanabilecek benzersiz bir işlemi tanımlar. Mevcut bağlamda, bir bağlantı noktası Windows Yuvaları destekleyen bir uygulamayla ilişkilendirilir. Aynı anda bir makinede çalışan birden fazla Windows Sockets uygulamanız olması için, her bir Windows Sockets uygulamasını benzersiz bir şekilde tanımlamak yararlı olacaktır.

Belirli bağlantı noktaları, FTP gibi ortak hizmetler için ayrılmıştır. Bu tür bir hizmet sağlamadığınız müddetçe bu bağlantı noktalarını kullanmaktan kaçının. Windows Yuvaları belirtimi, bu ayrılmış bağlantı noktalarının ayrıntılarını altında. Dosya WINSOCK. H ayrıca bunları listeler.

Windows Sockets DLL 'inin sizin için kullanılabilir bir bağlantı noktası seçmesini sağlamak için, bağlantı noktası değeri olarak 0 geçirin. MFC 1.024 ondalık değerinden büyük bir bağlantı noktası değeri seçer. [CAsyncSocket:: GetSockName](../mfc/reference/casyncsocket-class.md#getsockname) üye işlevini ÇAĞıRARAK, MFC 'nin seçtiği bağlantı noktası değerini alabilirsiniz.

## <a name="socket-address"></a><a name="_core_socket_address"></a> Yuva adresi

Her yuva nesnesi, ağdaki bir Internet Protokolü (IP) adresi ile ilişkilendirilir. Genellikle, adres, "ftp.microsoft.com" gibi bir makine adı veya "128.56.22.8" gibi noktalı bir sayı olur.

Yuva oluşturmak için arama yaptığınızda genellikle kendi adresinizi belirtmeniz gerekmez.

> [!NOTE]
> Makinenizin birden çok ağ kartına (ya da uygulamanız böyle bir makine üzerinde çalışabilir), her biri farklı bir ağı temsil eden bir durum olabilir. Bu durumda, yuvanın kullanacağı ağ kartını belirtmek için bir adres vermeniz gerekebilir. Bu, Gelişmiş kullanım ve olası bir taşınabilirlik sorunu olması açısından önemlidir.

Daha fazla bilgi için bkz:

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: yuvalar, arşivleri ile nasıl çalışır?](../mfc/windows-sockets-how-sockets-with-archives-work.md)

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
