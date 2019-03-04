---
title: Internet İstemci Sınıfları için Önkoşullar
ms.date: 11/04/2016
helpviewer_keywords:
- Internet files [MFC], writing to
- Internet [MFC], connections
- FTP (File Transfer Protocol), MFC classes
- Gopher prerequisites [MFC]
- files [MFC], writing to
- classes [MFC], connections
- HTTP [MFC], prerequisites for Internet clients
- connections [MFC], classes for
- Internet client class prerequisites [MFC]
- files [MFC], reading
- URLs [MFC], Internet client applications
- prerequisites, Internet client classes [MFC]
- Gopher client applications [MFC]
ms.assetid: c51d1dfe-260c-4228-8100-e4efd90e9599
ms.openlocfilehash: 6246db7dfb2837f5d94fa51f8433b46722c43663
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267751"
---
# <a name="prerequisites-for-internet-client-classes"></a>Internet İstemci Sınıfları için Önkoşullar

Bir Internet istemcisi (örneğin dosya okuma) tarafından gerçekleştirilen bazı eylemler önkoşul eylemlerinde (Internet bağlantısı oluşturma bu durumda). Aşağıdaki tablolar, bazı istemci eylemleri için önkoşulları listeler.

### <a name="general-internet-url-ftp-gopher-or-http"></a>Genel Internet URL (FTP, Gopher veya HTTP)

|Eylem|Önkoşul|
|------------|------------------|
|Bağlantı kurun.|Oluşturma bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) Internet istemci uygulaması temeli oluşturmak için.|
|Bir URL'yi açabilir.|Bağlantı kurun. Çağrı [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). `OpenURL` İşlevi bir salt okunur kaynak nesnesi döndürür.|
|Veri okuma URL'si.|URL'yi açın. Çağrı [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|
|Internet'seçeneğini ayarlayın.|Bağlantı kurun. Çağrı [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|
|Durum bilgileri ile çağrılacak bir işlev olarak ayarlayın.|Bağlantı kurun. Çağrı [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback). Geçersiz kılma [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) çağrıları işlemek için.|

### <a name="ftp"></a>FTP

|Eylem|Önkoşul|
|------------|------------------|
|Bir FTP bağlantı kurun.|Oluşturma bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) bu Internet istemci uygulaması temeli olarak. Çağrı [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection) oluşturmak için bir [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesne.|
|İlk kaynak bulun.|Bir FTP bağlantı kurun. Oluşturma bir [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) nesne. Çağrı [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|
|Tüm kullanılabilir kaynakları numaralandırılamadı.|İlk dosyayı bulun. Çağrı [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile) kadar false değerini döndürür.|
|Bir FTP dosyasını açın.|Bir FTP bağlantı kurun. Çağrı [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile) oluşturmak ve açmak için bir [Cınternetfile](../mfc/reference/cinternetfile-class.md) nesne.|
|Bir FTP dosyasını okuyun.|Bir FTP dosyasını okuma erişimi ile açın. Çağrı [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|
|Bir FTP dosyasına yazar.|Bir FTP dosyası yazma erişimi ile açın. Çağrı [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|
|Sunucusundaki istemcinin dizinine değiştirin.|Bir FTP bağlantı kurun. Çağrı [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|
|İstemcinin geçerli dizin sunucusundaki alın.|Bir FTP bağlantı kurun. Çağrı [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory).|

### <a name="http"></a>HTTP

|Eylem|Önkoşul|
|------------|------------------|
|Bir HTTP bağlantısı kurun.|Oluşturma bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) bu Internet istemci uygulaması temeli olarak. Çağrı [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection) oluşturmak için bir [CHttpConnection](../mfc/reference/chttpconnection-class.md) nesne.|
|HTTP dosyasını açın.|Bir HTTP bağlantısı kurun. Çağrı [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) oluşturmak için bir [CHttpFile](../mfc/reference/chttpfile-class.md) nesne. Çağrı [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders). Çağrı [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|
|HTTP dosyasını okuyun.|HTTP dosyasını açın. Çağrı [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|
|Bir HTTP isteği hakkında bilgi alın.|Bir HTTP bağlantısı kurun. Çağrı [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) oluşturmak için bir [CHttpFile](../mfc/reference/chttpfile-class.md) nesne. Çağrı [CHttpFile::QueryInfo](../mfc/reference/chttpfile-class.md#queryinfo).|

### <a name="gopher"></a>Gopher

|Eylem|Önkoşul|
|------------|------------------|
|Bir gopher bağlantı kurun.|Oluşturma bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) bu Internet istemci uygulaması temeli olarak. Çağrı [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection) oluşturmak için bir [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|
|İlk dosyayı geçerli dizinde bulun.|Bir gopher bağlantı kurun. Oluşturma bir [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) nesne. Çağrı [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) oluşturmak için bir [CGopherLocator](../mfc/reference/cgopherlocator-class.md) nesne. Bulucu için geçirmek [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile). Çağrı [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator) daha sonra ihtiyacınız varsa, bir dosyanın Bulucu almak için.|
|Tüm kullanılabilir dosyaları sıralar.|İlk dosyayı bulun. Çağrı [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) kadar false değerini döndürür.|
|Bir gopher dosyasını açın.|Bir gopher bağlantı kurun. Bir gopher ile Bulucu [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) veya bulma ile bir Bulucu [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Çağrı [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|
|Bir gopher dosyasını okuyun.|Bir gopher dosyasını açın. Kullanım [CGopherFile](../mfc/reference/cgopherfile-class.md).|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet İstemci Uygulamaları Oluşturmak için MFC Sınıfları](../mfc/mfc-classes-for-creating-internet-client-applications.md)<br/>
[MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
