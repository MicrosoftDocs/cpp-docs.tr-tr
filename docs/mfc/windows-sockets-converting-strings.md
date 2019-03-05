---
title: 'Windows Yuvaları: Dizeleri dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: eaf278fc2689f0afa9ab6ff30f1294c36de5d7ac
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298369"
---
# <a name="windows-sockets-converting-strings"></a>Windows Yuvaları: Dizeleri dönüştürme

Bu makale ve iki Yardımcısı makaleler Windows Sockets programlamada çeşitli sorunlar açıklanmaktadır. Bu makale, dizeleri dönüştürme kapsar. Diğer sorunlar ele alınmaktadır [Windows Yuvaları: Engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Yuvaları: Bayt sıralama](../mfc/windows-sockets-byte-ordering.md).

Kullanıyorsanız veya sınıfından türetilir [Casyncsocket'ini](../mfc/reference/casyncsocket-class.md), bu sorunları kendiniz yönetmeniz gerekecek. Kullanıyorsanız veya sınıfından türetilir [CSocket](../mfc/reference/csocket-class.md), MFC yönetir bunlar sizin için.

## <a name="converting-strings"></a>Dizeleri dönüştürme

Veya bunlardan birini ve ANSI karakter dizeleri kullanan bir uygulamanın farklı geniş karakter biçimlerinde depolanan dizeleri Unicode veya çok baytlı karakter (MBCS) ayarlar gibi kullanan uygulamalar arasında iletişim kurmak, dönüştürmeler yönetmelidir kendiniz altında `CAsyncSocket`. `CArchive` Nesne ile kullanılan bir `CSocket` nesnesi yönetir, bu dönüştürme için özellikleri sınıfın [CString](../atl-mfc-shared/reference/cstringt-class.md). Daha fazla bilgi için bkz: Windows SDK'da bulunan Windows yuva belirtimi.

Daha fazla bilgi için bkz.:

- [Windows Yuvaları: Sınıf Casyncsocket'ini kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Yuvaları Arşivlerle kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Arka plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: Stream yuva](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: Veri birimi yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
