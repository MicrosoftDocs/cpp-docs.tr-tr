---
description: 'Daha fazla bilgi edinin: Internet Istemci sınıfları için Önkoşullar'
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
ms.openlocfilehash: 9159aa6b3ae4918e406524be05e00fca66cd28a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205882"
---
# <a name="prerequisites-for-internet-client-classes"></a>Internet İstemci Sınıfları için Önkoşullar

Bir Internet istemcisi tarafından gerçekleştirilen bazı eylemler (örneğin, bir dosyayı okumak) önkoşul eylemlerine sahiptir (Bu durumda, bir Internet bağlantısı kurmak). Aşağıdaki tablolarda bazı istemci eylemlerinin önkoşulları listelenmektedir.

### <a name="general-internet-url-ftp-gopher-or-http"></a>Genel Internet URL 'SI (FTP, Gopher veya HTTP)

|Eylem|Önkoşul|
|------------|------------------|
|Bir bağlantı kurun.|Bir Internet istemci uygulamasının temelini oluşturmak için bir [CInternetSession](reference/cinternetsession-class.md) oluşturun.|
|URL 'YI açın.|Bir bağlantı kurun. [CInternetSession:: OpenURL 'yi](reference/cinternetsession-class.md#openurl)çağırın. `OpenURL`İşlev, salt okunurdur kaynak nesne döndürür.|
|URL verilerini okuyun.|URL 'YI açın. [CInternetFile:: Read](reference/cinternetfile-class.md#read)öğesini çağırın.|
|Internet seçeneğini ayarlayın.|Bir bağlantı kurun. [CInternetSession:: SetOption](reference/cinternetsession-class.md#setoption)çağrısı yapın.|
|Durum bilgileriyle çağrılacak bir işlev ayarlayın.|Bir bağlantı kurun. [CInternetSession:: EnableStatusCallback](reference/cinternetsession-class.md#enablestatuscallback)öğesini çağırın. Çağrıları işlemek için [CInternetSession:: OnStatusCallback](reference/cinternetsession-class.md#onstatuscallback) öğesini geçersiz kılın.|

### <a name="ftp"></a>FTP

|Eylem|Önkoşul|
|------------|------------------|
|FTP bağlantısı kurun.|Bu Internet istemci uygulamasının temeli olarak bir [CInternetSession](reference/cinternetsession-class.md) oluşturun. [CInternetSession:: GetFtpConnection](reference/cinternetsession-class.md#getftpconnection) öğesini çağırıp [CFtpConnection](reference/cftpconnection-class.md) nesnesi oluşturun.|
|İlk kaynağı bulun.|FTP bağlantısı kurun. [CFtpFileFind](reference/cftpfilefind-class.md) nesnesi oluşturun. [CFtpFileFind:: FindFile](reference/cftpfilefind-class.md#findfile)öğesini çağırın.|
|Tüm kullanılabilir kaynakları numaralandırın.|İlk dosyayı bulun. FALSE değerini alıncaya kadar [CFtpFileFind:: FindNextFile](reference/cftpfilefind-class.md#findnextfile) öğesini çağırın.|
|Bir FTP dosyası açın.|FTP bağlantısı kurun. [CInternetFile](reference/cinternetfile-class.md) nesnesi oluşturup açmak Için [CFtpConnection:: OpenFile](reference/cftpconnection-class.md#openfile) öğesini çağırın.|
|FTP dosyası okuyun.|Okuma erişimi olan bir FTP dosyası açın. [CInternetFile:: Read](reference/cinternetfile-class.md#read)öğesini çağırın.|
|FTP dosyasına yazın.|Yazma erişimi olan bir FTP dosyası açın. [CInternetFile:: Write](reference/cinternetfile-class.md#write)öğesini çağırın.|
|Sunucuda istemcinin dizinini değiştirin.|FTP bağlantısı kurun. [CFtpConnection:: SetCurrentDirectory](reference/cftpconnection-class.md#setcurrentdirectory)öğesini çağırın.|
|İstemcinin geçerli dizinini sunucuda alın.|FTP bağlantısı kurun. [CFtpConnection:: GetCurrentDirectory](reference/cftpconnection-class.md#getcurrentdirectory)öğesini çağırın.|

### <a name="http"></a>HTTP

|Eylem|Önkoşul|
|------------|------------------|
|HTTP bağlantısı kurun.|Bu Internet istemci uygulamasının temeli olarak bir [CInternetSession](reference/cinternetsession-class.md) oluşturun. [CHttpConnection](reference/chttpconnection-class.md) nesnesi oluşturmak Için [CInternetSession:: GetHttpConnection](reference/cinternetsession-class.md#gethttpconnection) öğesini çağırın.|
|Bir HTTP dosyası açın.|HTTP bağlantısı kurun. [CHttpFile](reference/chttpfile-class.md) nesnesi oluşturmak için [CHttpConnection:: OpenRequest](reference/chttpconnection-class.md#openrequest) çağırın. [CHttpFile:: AddRequestHeaders](reference/chttpfile-class.md#addrequestheaders)öğesini çağırın. [CHttpFile:: SendRequest](reference/chttpfile-class.md#sendrequest)öğesini çağırın.|
|Bir HTTP dosyası okuyun.|Bir HTTP dosyası açın. [CInternetFile:: Read](reference/cinternetfile-class.md#read)öğesini çağırın.|
|Bir HTTP isteği hakkında bilgi alın.|HTTP bağlantısı kurun. [CHttpFile](reference/chttpfile-class.md) nesnesi oluşturmak için [CHttpConnection:: OpenRequest](reference/chttpconnection-class.md#openrequest) çağırın. [CHttpFile:: QueryInfo](reference/chttpfile-class.md#queryinfo)çağırın.|

### <a name="gopher"></a>Gopher

|Eylem|Önkoşul|
|------------|------------------|
|Gopher bağlantısı kurun.|Bu Internet istemci uygulamasının temeli olarak bir [CInternetSession](reference/cinternetsession-class.md) oluşturun. [CInternetSession:: GetGopherConnection](reference/cinternetsession-class.md#getgopherconnection) öğesini çağırıp bir [CGopherConnection](reference/cgopherconnection-class.md)oluşturun.|
|Geçerli dizindeki ilk dosyayı bulun.|Gopher bağlantısı kurun. Bir [CGopherFileFind](reference/cgopherfilefind-class.md) nesnesi oluşturun. Bir [CGopherLocator](reference/cgopherlocator-class.md) nesnesi oluşturmak Için [CGopherConnection:: CreateLocator](reference/cgopherconnection-class.md#createlocator) öğesini çağırın. Bulucuyu [CGopherFileFind:: FindFile](reference/cgopherfilefind-class.md#findfile)öğesine geçirin. Daha sonra ihtiyacınız varsa, bir dosyanın Konumlandırıcı 'sını almak için [CGopherFileFind:: GetLocator](reference/cgopherfilefind-class.md#getlocator) öğesini çağırın.|
|Kullanılabilir tüm dosyaları numaralandırın.|İlk dosyayı bulun. FALSE değerini alıncaya kadar [CGopherFileFind:: FindNextFile](reference/cgopherfilefind-class.md#findnextfile) öğesini çağırın.|
|Bir gopher dosyası açın.|Gopher bağlantısı kurun. [CGopherConnection:: CreateLocator](reference/cgopherconnection-class.md#createlocator) ile bir Gopher Bulucu oluşturun veya [CGopherFileFind:: GetLocator](reference/cgopherfilefind-class.md#getlocator)ile bir bulucu bulun. [CGopherConnection:: OpenFile](reference/cgopherconnection-class.md#openfile)çağrısı yapın.|
|Bir gopher dosyası okuyun.|Bir gopher dosyası açın. [CGopherFile](reference/cgopherfile-class.md)kullanın.|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](win32-internet-extensions-wininet.md)<br/>
[Internet Istemci uygulamaları oluşturmak için MFC sınıfları](mfc-classes-for-creating-internet-client-applications.md)<br/>
[MFC WinINet sınıfları kullanarak Internet Istemci uygulaması yazma](writing-an-internet-client-application-using-mfc-wininet-classes.md)
