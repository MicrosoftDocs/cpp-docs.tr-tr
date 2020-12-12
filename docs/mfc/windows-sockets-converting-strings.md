---
description: 'Daha fazla bilgi edinin: Windows Yuvaları: dizeleri dönüştürme'
title: 'Windows Yuvaları: Dizeleri Dönüştürme'
ms.date: 11/04/2016
helpviewer_keywords:
- Windows Sockets [MFC], multibyte character string conversion
- sockets [MFC], multibyte character string conversion issues
- string conversion, multibyte character strings
ms.assetid: 9df522b5-6b23-41e0-bb96-e4e623baf141
ms.openlocfilehash: fe8607647192fadc7f0d5d32d7716c222ff9206f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118634"
---
# <a name="windows-sockets-converting-strings"></a>Windows Yuvaları: Dizeleri Dönüştürme

Bu makalede ve iki yardımcı makalede Windows Sockets programlamasında çeşitli sorunlar açıklanmaktadır. Bu makale, dizeleri dönüştürmeyi içerir. [Windows Yuvaları: engelleme](../mfc/windows-sockets-blocking.md) ve [Windows Yuvaları: bayt sıralaması](../mfc/windows-sockets-byte-ordering.md)kapsamında diğer sorunlar ele alınmıştır.

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)sınıfından kullanırsanız veya türetirsiniz, bu sorunları kendiniz yönetmeniz gerekecektir. [CSocket](../mfc/reference/csocket-class.md)sınıfından kullanırsanız veya türetirsiniz, MFC bunları sizin için yönetir.

## <a name="converting-strings"></a>Dizeleri Dönüştürme

Unicode veya çok baytlı karakter kümeleri (MBCS) gibi farklı geniş karakter biçimlerinde depolanan dizeleri kullanan uygulamalar arasında iletişim kurmanızı istiyorsanız veya bunlardan biri ile ANSI karakter dizelerini kullanarak bir uygulama arasında iletişim kurmak isterseniz, dönüştürmeleri ' de kendiniz yönetmeniz gerekir `CAsyncSocket` . `CArchive`Nesnesiyle kullanılan nesne, `CSocket` [CString](../atl-mfc-shared/reference/cstringt-class.md)sınıfının özellikleri boyunca bu dönüştürmeyi yönetir. Daha fazla bilgi için, Windows SDK bulunan Windows Yuvaları belirtimine bakın.

Daha fazla bilgi için bkz:

- [Windows Yuvaları: sınıf CAsyncSocket kullanma](../mfc/windows-sockets-using-class-casyncsocket.md)

- [Windows Yuvaları: Arşivlerle yuvaları kullanma](../mfc/windows-sockets-using-sockets-with-archives.md)

- [Windows Yuvaları: Arka Plan](../mfc/windows-sockets-background.md)

- [Windows Yuvaları: akış Yuvaları](../mfc/windows-sockets-stream-sockets.md)

- [Windows Yuvaları: veri birimi Yuvaları](../mfc/windows-sockets-datagram-sockets.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC'de Windows Yuvaları](../mfc/windows-sockets-in-mfc.md)
