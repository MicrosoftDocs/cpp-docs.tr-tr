---
title: Tipik bir FTP istemci uygulamasında adımlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7fe5a55afda9e77db6e8baddd68c09f4250071bb
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951207"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Tipik Bir FTP İstemci Uygulamasındaki Adımlar
Tipik bir FTP istemci uygulaması oluşturur bir [CInternetSession](../mfc/reference/cinternetsession-class.md) ve [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesnesi. Bu MFC WinINet sınıfları gerçekte proxy türü ayarlarını kontrol etmez olduğunu unutmayın; IIS yapar.  
  
 Ayrıca, bu Bilgi Bankası makalelerine bakın:  
  
-   Nasıl yapılır: FTP Proxy WinINet API kullanarak CERN tabanlı (makale No: Q166961)  
  
-   Örnek: Proxy FTP CERN tabanlı parolayla korunan (makale No: Q216214)  
  
-   Internet Hizmetleri Yöneticisi yüklü Proxy Hizmetleri göstermek için başarısız (makale No: Q216802)  
  
 Aşağıdaki tabloda, tipik bir FTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.  
  
|Amacınız|Eylemleri|Etkiler|  
|---------------|----------------------|-------------|  
|Bir FTP oturumunun başlayın.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|WinINet başlatır ve sunucusuna bağlanır.|  
|Bir FTP sunucusuna bağlanın.|Kullanım [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Döndürür bir [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesnesi.|  
|Sunucuda yeni bir FTP dizinine geçin.|Kullanım [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Şu anda sunucu üzerinde bağlı dizini değiştirir.|  
|İlk dosya FTP dizinde bulun.|Kullanım [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|İlk dosyayı bulur. Hiçbir dosya bulunamazsa FALSE döndürür.|  
|Sonraki dosyasını FTP dizinde bulun.|Kullanım [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sonraki dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|  
|Tarafından bulunan dosya açmak `FindFile` veya `FindNextFile` okuma veya yazma.|Kullanım [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile), dosya adını kullanarak döndürülen [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) veya ['larını](../mfc/reference/cftpfilefind-class.md#findnextfile).|Okuma veya yazma için dosya sunucusunda açılır. Döndürür bir [CInternetFile](../mfc/reference/cinternetfile-class.md) nesnesi.|  
|Okuma veya dosyaya yazmak.|Kullanım [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read) veya [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|Okur veya belirtilen sayıda baytı, sağladığınız arabellek kullanarak yazar.|  
|Özel durumları işleme.|Kullanım [CInternetException](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türleri işler.|  
|FTP oturumunu sonlandırın.|Elden [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|Otomatik olarak açık dosya tanıtıcıları ve bağlantıları temizler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet İstemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
