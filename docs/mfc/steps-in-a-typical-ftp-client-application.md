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
ms.openlocfilehash: d87682d9110aa37fbb806f7d1dcd70009cf2ad63
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46406964"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Tipik Bir FTP İstemci Uygulamasındaki Adımlar

Tipik bir FTP istemci uygulaması oluşturan bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) ve [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesne. Bu MFC WinINet sınıfları gerçekten proxy türü ayarlarını kontrol olduğunu unutmayın. IIS yapar.

Ayrıca, bu Bilgi Bankası makalelerine bakın:

- Nasıl yapılır: FTP ile CERN tabanlı Proxy WinINet API kullanarak (makale kimliği: Q166961)

- Örnek: Proxy FTP CERN tabanlı parola ile korunan (makale kimliği: Q216214)

- Internet Hizmetleri Yöneticisi yüklü Proxy Hizmetleri göstermek için başarısız (makale kimliği: Q216802)

Aşağıdaki tabloda, tipik bir FTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.

|Amacınız|İşlemlerde|Etkiler|
|---------------|----------------------|-------------|
|Bir FTP oturumunun başlayın.|Oluşturma bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) nesne.|WinINet başlatır ve sunucusuna bağlanır.|
|Bir FTP sunucusuna bağlanın.|Kullanım [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Döndürür bir [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesne.|
|Sunucuda yeni bir FTP dizinine geçin.|Kullanım [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Şu anda sunucu üzerinde bağlıyken dizinini değiştirir.|
|FTP dizin ilk dosyayı bulun.|Kullanım [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|İlk dosya bulur. Dosya bulunamazsa false değerini döndürür.|
|FTP dizin sonraki dosyasını bulun.|Kullanım [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sonraki dosya bulur. Dosya bulunamazsa false değerini döndürür.|
|Tarafından bulunan dosyayı açmak `FindFile` veya `FindNextFile` okuma veya yazma için.|Kullanım [CFtpConnection::OpenFile](../mfc/reference/cftpconnection-class.md#openfile), tarafından döndürülen dosya adını kullanarak [FindFile](../mfc/reference/cftpfilefind-class.md#findfile) veya ['larını](../mfc/reference/cftpfilefind-class.md#findnextfile).|Dosya sunucusunda okuma veya yazma için açar. Döndürür bir [Cınternetfile](../mfc/reference/cinternetfile-class.md) nesne.|
|Okuma veya dosyaya yazmak.|Kullanım [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read) veya [CInternetFile::Write](../mfc/reference/cinternetfile-class.md#write).|Okur veya sağladığınız bir arabelleği kullanarak belirtilen sayıda yazar.|
|Özel durumları işler.|Kullanım [Cınternetexception](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türlerini işler.|
|FTP oturumunu sonlandırın.|Elden [Cınternetsession](../mfc/reference/cinternetsession-class.md) nesne.|Dosya tanıtıcılarını Aç ve bağlantıları tarafından otomatik olarak temizlenir.|

## <a name="see-also"></a>Ayrıca Bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet İstemci Sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
