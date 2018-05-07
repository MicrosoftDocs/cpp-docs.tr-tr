---
title: Internet İstemci sınıfları için Önkoşullar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6c16c3658ee5d27def4892997c50115dc0b8831
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="prerequisites-for-internet-client-classes"></a>Internet İstemci Sınıfları için Önkoşullar
(Örneğin bir dosya okuma) bir Internet istemcisi tarafından yapılan bazı eylemler önkoşul eylemleri (bir Internet bağlantısı kurmadan bu durumda,) sahip. Aşağıdaki tablolar, bazı istemci eylemleri için önkoşulları listeler.  
  
### <a name="general-internet-url-ftp-gopher-or-http"></a>Genel Internet URL (FTP, Gopher veya HTTP)  
  
|Eylem|Önkoşul|  
|------------|------------------|  
|Bağlantı kurun.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) Internet istemci uygulaması temeli oluşturmak için.|  
|Bir URL açın.|Bağlantı kurun. Çağrı [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl). `OpenURL` İşlevi bir salt okunur kaynak nesnesi döndürür.|  
|Okuma URL verileri.|URL'yi açın. Çağrı [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|  
|Bir Internet seçeneğini ayarlayın.|Bağlantı kurun. Çağrı [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|  
|Durum bilgileriyle çağrılacak işlev ayarlayın.|Bağlantı kurun. Çağrı [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback). Geçersiz kılma [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback) çağrıları işlemek için.|  
  
### <a name="ftp"></a>FTP  
  
|Eylem|Önkoşul|  
|------------|------------------|  
|Bir FTP bağlantısı kurun.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) bu Internet istemci uygulaması temeli olarak. Çağrı [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection) oluşturmak için bir [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesnesi.|  
|İlk kaynak bulunamıyor.|Bir FTP bağlantısı kurun. Oluşturma bir [CFtpFileFind](../mfc/reference/cftpfilefind-class.md) nesnesi. Çağrı [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|  
|Tüm kullanılabilir kaynakları numaralandırılamıyor.|İlk dosyasını bulun. Çağrı [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile) kadar FALSE değerini döndürür.|  
|Bir FTP dosyasını açın.|Bir FTP bağlantısı kurun. Çağrı [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile) oluşturmak ve açmak için bir [CInternetFile](../mfc/reference/cinternetfile-class.md) nesnesi.|  
|Bir FTP dosyasını okuyun.|Bir FTP dosyasını okuma erişimi ile açın. Çağrı [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|  
|Bir FTP dosyasına yazar.|Yazma erişimi bir FTP dosyasını açın. Çağrı [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|  
|Sunucusunda istemcinin dizinine değiştirin.|Bir FTP bağlantısı kurun. Çağrı [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|  
|Sunucusunda istemcinin geçerli dizinin alın.|Bir FTP bağlantısı kurun. Çağrı [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory).|  
  
### <a name="http"></a>HTTP  
  
|Eylem|Önkoşul|  
|------------|------------------|  
|Bir HTTP bağlantısı kurun.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) bu Internet istemci uygulaması temeli olarak. Çağrı [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection) oluşturmak için bir [CHttpConnection](../mfc/reference/chttpconnection-class.md) nesnesi.|  
|Bir HTTP dosyasını açın.|Bir HTTP bağlantısı kurun. Çağrı [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) oluşturmak için bir [CHttpFile](../mfc/reference/chttpfile-class.md) nesnesi. Çağrı [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders). Çağrı [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|  
|Bir HTTP dosyasını okuyun.|Bir HTTP dosyasını açın. Çağrı [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|  
|Bir HTTP isteği hakkında bilgi alın.|Bir HTTP bağlantısı kurun. Çağrı [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest) oluşturmak için bir [CHttpFile](../mfc/reference/chttpfile-class.md) nesnesi. Çağrı [CHttpFile::QueryInfo](../mfc/reference/chttpfile-class.md#queryinfo).|  
  
### <a name="gopher"></a>Gopher  
  
|Eylem|Önkoşul|  
|------------|------------------|  
|Gopher bağlantı kurun.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) bu Internet istemci uygulaması temeli olarak. Çağrı [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection) oluşturmak için bir [CGopherConnection](../mfc/reference/cgopherconnection-class.md).|  
|İlk dosya geçerli dizinde bulunamadı.|Gopher bağlantı kurun. Oluşturma bir [CGopherFileFind](../mfc/reference/cgopherfilefind-class.md) nesnesi. Çağrı [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) oluşturmak için bir [CGopherLocator](../mfc/reference/cgopherlocator-class.md) nesnesi. Bulucu geçirmek [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile). Çağrı [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator) daha sonra gerekirse bir dosya Bulucu alınamıyor.|  
|Kullanılabilir tüm dosyalar sıralar.|İlk dosyasını bulun. Çağrı [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile) kadar FALSE değerini döndürür.|  
|Gopher dosyasını açın.|Gopher bağlantı kurun. Gopher bulucuyla oluşturma [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator) veya bir Bulucu ile Bul [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Çağrı [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|  
|Gopher dosyasını okuyun.|Gopher dosyasını açın. Kullanım [CGopherFile](../mfc/reference/cgopherfile-class.md).|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet istemci uygulamaları oluşturmak için MFC sınıfları](../mfc/mfc-classes-for-creating-internet-client-applications.md)   
 [MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
