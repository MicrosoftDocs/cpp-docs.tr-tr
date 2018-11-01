---
title: MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC]
- WinInet classes [MFC], programming
- Internet client applications [MFC], writing
- Internet applications [MFC], WinInet
- Internet applications [MFC], client applications
- MFC, Internet applications
ms.assetid: a2c4a40c-a94e-4b3e-9dbf-f8a8dc8e5428
ms.openlocfilehash: 041fa90b030edd9b5324c183b0153a8a062735da
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50494971"
---
# <a name="writing-an-internet-client-application-using-mfc-wininet-classes"></a>MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma

Her bir Internet istemci uygulaması Internet oturumu temelidir. MFC uygulayan sınıfın nesneleri olarak Internet oturumu [Cınternetsession](../mfc/reference/cinternetsession-class.md). Bu sınıfı kullanarak Internet oturumu bir veya birden çok eşzamanlı oturumlar oluşturabilirsiniz.

Bir sunucu ile iletişim kurmak için gereken bir [Cınternetconnection](../mfc/reference/cinternetconnection-class.md) nesne yanı sıra bir `CInternetSession`. Oluşturabileceğiniz bir `CInternetConnection` kullanarak [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection), [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection), veya [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection). Protokol türü için bu çağrılardan her özeldir. Bu çağrıları, okuma veya yazma için bir dosya sunucusundaki açmayın. Verileri okuma veya yazma yapmak istiyorsanız, ayrı bir adım olarak dosyasını açmanız gerekir.

Çoğu Internet oturumlar için `CInternetSession` nesne el el ile çalışan bir [Cınternetfile](../mfc/reference/cinternetfile-class.md) nesnesi:

- Bir Internet oturumu için bir örneğini oluşturmanız gerekir [Cınternetsession](../mfc/reference/cinternetsession-class.md).

- Internet oturumunuz okur ya da verileri yazar örneğini oluşturmalısınız `CInternetFile` (veya alt sınıflara [CHttpFile](../mfc/reference/chttpfile-class.md) veya [CGopherFile](../mfc/reference/cgopherfile-class.md)). Verileri okumak için en kolay yolu çağırmaktır [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). Bu işlev bir Evrensel Kaynak Konum Belirleyicisi (sizin tarafınızdan sağlanan URL) ayrıştırır, URL ile belirtilen sunucunun bir bağlantı açar ve salt okunur döndürür `CInternetFile` nesne. `CInternetSession::OpenURL` bir protokol türüne özgü değildir — aynı çağrı için FTP, HTTP veya gopher URL çalışır. `CInternetSession::OpenURL` Yerel dosyalarla'da çalışır (döndüren bir `CStdioFile` yerine bir `CInternetFile`).

- Internet oturumu okumaz veya veri yazma ancak gerçekleştiriyorsa bir FTP dizindeki bir dosya silindiğinde gibi diğer görevleri bir örneğini oluşturmak gerekmez `CInternetFile`.

Oluşturmanın iki yolu vardır. bir `CInternetFile` nesnesi:

- Kullanırsanız `CInternetSession::OpenURL` çağrısı, sunucu bağlantısı kurmak için `OpenURL` döndürür bir `CStdioFile`.

- Varsa kullanın `CInternetSession::GetFtpConnection`, `GetGopherConnection`, veya `GetHttpConnection` sunucu bağlantınızı kurmak için çağırmalısınız `CFtpConnection::OpenFile`, `CGopherConnection::OpenFile`, veya `CHttpConnection::OpenRequest`, sırasıyla döndürülecek bir `CInternetFile`, `CGopherFile`, veya `CHttpFile`, sırasıyla.

Bir Internet istemci uygulaması gerçekleştirilmesinin adımları, temel, genel bir Internet istemcisi oluşturduğunuz bağlı olarak farklılık `OpenURL` veya birini kullanarak bir protokole özgü istemci `GetConnection` işlevleri.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Genel FTP, HTTP ve gopher ile çalışan Internet istemci uygulaması nasıl yazılır](../mfc/steps-in-a-typical-internet-client-application.md)

- [Bir dosya açar bir FTP istemci uygulaması nasıl yazılır](../mfc/steps-in-a-typical-ftp-client-application.md)

- [Bir dosya açılmaz ancak bir dosya silindiğinde gibi bir dizin işlemi gerçekleştiren bir FTP istemci uygulama nasıl yazılır](../mfc/steps-in-a-typical-ftp-client-application-to-delete-a-file.md)

- [Bir gopher istemci uygulamasını nasıl yazılır](../mfc/steps-in-a-typical-gopher-client-application.md)

- [HTTP istemci uygulamanın nasıl yazılır](../mfc/steps-in-a-typical-http-client-application.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet İstemci Uygulamaları Oluşturmak için MFC Sınıfları](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[Internet İstemci Sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)
