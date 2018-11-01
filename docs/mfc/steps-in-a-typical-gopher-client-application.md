---
title: Tipik Bir Gopher İstemci Uygulamasındaki Adımlar
ms.date: 11/04/2016
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
ms.openlocfilehash: 123b8abd2ca65356c584fa52f9415504bcb701c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486430"
---
# <a name="steps-in-a-typical-gopher-client-application"></a>Tipik Bir Gopher İstemci Uygulamasındaki Adımlar

Aşağıdaki tabloda, tipik bir gopher istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.

|Amacınız|İşlemlerde|Etkiler|
|---------------|----------------------|-------------|
|Bir gopher oturumu başlayın.|Oluşturma bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) nesne.|WinINet başlatır ve sunucusuna bağlanır.|
|Bir gopher sunucusuna bağlanın.|Kullanım [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection).|Döndürür bir [CGopherConnection](../mfc/reference/cgopherconnection-class.md) nesne.|
|İlk kaynak içinde bir gopher bulun.|Kullanım [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile).|İlk dosya bulur. Dosya bulunamazsa false değerini döndürür.|
|Sonraki kaynak içinde bir gopher bulun.|Kullanım [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile).|Sonraki dosya bulur. Dosya bulunamazsa false değerini döndürür.|
|Tarafından bulunan dosyayı açmak `FindFile` veya `FindNextFile` okuma için.|Kullanarak bir gopher Bulucu alma [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Kullanım [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Bulucu tarafından belirtilen dosyayı açar. `OpenFile` döndürür bir [CGopherFile](../mfc/reference/cgopherfile-class.md) nesne.|
|Sağladığınız bir gopher Bulucu kullanarak bir dosyayı açın.|Kullanarak bir gopher Bulucu [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator). Kullanım [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Bulucu tarafından belirtilen dosyayı açar. `OpenFile` döndürür bir [CGopherFile](../mfc/reference/cgopherfile-class.md) nesne.|
|Dosyadan okuma.|Kullanım [CGopherFile](../mfc/reference/cgopherfile-class.md).|Sağladığınız bir arabelleği kullanarak belirtilen sayıda okur.|
|Özel durumları işler.|Kullanım [Cınternetexception](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türlerini işler.|
|Gopher oturumunu sonlandırın.|Elden [Cınternetsession](../mfc/reference/cinternetsession-class.md) nesne.|Dosya tanıtıcılarını Aç ve bağlantıları tarafından otomatik olarak temizlenir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet İstemci Sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
