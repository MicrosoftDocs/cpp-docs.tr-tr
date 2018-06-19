---
title: 'Windows Yuvaları: Dizeleri dönüştürme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bad57be68ce716cddf2ce44f12e94c545a7bbfd6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33383766"
---
# <a name="windows-sockets-converting-strings"></a>Windows Yuvaları: Dizeleri Dönüştürme
Bu makale ve iki yardımcı makaleler Windows Sockets programlamada çeşitli sorunlar açıklanmaktadır. Bu makalede, dizeleri dönüştürme yer almaktadır. Diğer sorunlar ele alınmaktadır [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md).  
  
 Kullanıyorsanız veya sınıfından türetilen [CAsyncSocket](../mfc/reference/casyncsocket-class.md), bu sorunları kendiniz yönetmeniz gerekir. Kullanıyorsanız veya sınıfından türetilen [CSocket](../mfc/reference/csocket-class.md), MFC yönetir bunları sizin için.  
  
## <a name="converting-strings"></a>Dizeleri dönüştürme  
 Unicode ya da birden çok baytlı karakter (MBCS) ayarlar gibi farklı joker karakter biçimlerde depolanan dizeleri kullanan uygulamalar arasında ya da bunlardan birini ve ANSI karakter dizelerini kullanarak bir uygulama arasındaki iletişim halinde dönüşümleri yönetmeniz gerekir kendiniz altında `CAsyncSocket`. `CArchive` İle kullanılan nesnesi bir `CSocket` nesnesi yönetir bu dönüştürme için özellikleri aracılığıyla sınıfının [CString](../atl-mfc-shared/reference/cstringt-class.md). Daha fazla bilgi için bkz: Windows SDK'da bulunan Windows Sockets belirtimi.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Sınıf CAsyncSocket'ini Kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle Kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Yuvaları: Akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri Birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

