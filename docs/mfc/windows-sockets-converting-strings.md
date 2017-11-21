---
title: "Windows Yuvaları: Dizeleri dönüştürme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4b0b66cb83dc13f74e5417cab7f8cec0fe65b73a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-converting-strings"></a>Windows Yuvaları: Dizeleri Dönüştürme
Bu makale ve iki yardımcı makaleler Windows Sockets programlamada çeşitli sorunlar açıklanmaktadır. Bu makalede, dizeleri dönüştürme yer almaktadır. Diğer sorunlar ele alınmaktadır [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Yuvaları: bayt sıralama](../mfc/windows-sockets-byte-ordering.md).  
  
 Kullanıyorsanız veya sınıfından türetilen [CAsyncSocket](../mfc/reference/casyncsocket-class.md), bu sorunları kendiniz yönetmeniz gerekir. Kullanıyorsanız veya sınıfından türetilen [CSocket](../mfc/reference/csocket-class.md), MFC yönetir bunları sizin için.  
  
## <a name="converting-strings"></a>Dizeleri dönüştürme  
 Unicode ya da birden çok baytlı karakter (MBCS) ayarlar gibi farklı joker karakter biçimlerde depolanan dizeleri kullanan uygulamalar arasında ya da bunlardan birini ve ANSI karakter dizelerini kullanarak bir uygulama arasındaki iletişim halinde dönüşümleri yönetmeniz gerekir kendiniz altında `CAsyncSocket`. `CArchive` İle kullanılan nesnesi bir `CSocket` nesnesi yönetir bu dönüştürme için özellikleri aracılığıyla sınıfının [CString](../atl-mfc-shared/reference/cstringt-class.md). Daha fazla bilgi için bkz: Windows SDK'da bulunan Windows Sockets belirtimi.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Yuvaları: Yuvaları Arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Yuvaları: arka plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Yuvaları: Akış yuvaları](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Yuvaları: Veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)

