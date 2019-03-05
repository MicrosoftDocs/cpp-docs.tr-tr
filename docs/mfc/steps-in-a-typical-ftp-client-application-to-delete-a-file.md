---
title: Dosya Silmek için Tipik Bir FTP İstemci Uygulamasındaki Adımlar
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
ms.openlocfilehash: 6d2a920d3053a920638dd20a23e1c2334745bbc3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326510"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Dosya Silmek için Tipik Bir FTP İstemci Uygulamasındaki Adımlar

Aşağıdaki tabloda, bir dosyayı silen bir tipik FTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.

|Amacınız|İşlemlerde|Etkiler|
|---------------|----------------------|-------------|
|Bir FTP oturumunun başlayın.|Oluşturma bir [Cınternetsession](../mfc/reference/cinternetsession-class.md) nesne.|WinINet başlatır ve sunucusuna bağlanır.|
|Bir FTP sunucusuna bağlanın.|Kullanım [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Döndürür bir [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesne.|
|FTP sunucusunun doğru dizininde olduğunuzdan emin olmak için kontrol edin.|Kullanım [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) veya [CFtpConnection::GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl).|Adı veya URL'si şu anda sunucuda seçilen üye işlevi bağlı olarak, bağlı olduğunuz bir dizinin döndürür.|
|Sunucuda yeni bir FTP dizinine geçin.|Kullanım [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Şu anda sunucu üzerinde bağlıyken dizinini değiştirir.|
|FTP dizin ilk dosyayı bulun.|Kullanım [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|İlk dosya bulur. Dosya bulunamazsa false değerini döndürür.|
|FTP dizin sonraki dosyasını bulun.|Kullanım [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sonraki dosya bulur. Dosya bulunamazsa false değerini döndürür.|
|Tarafından bulunan dosya silme `FindFile` veya `FindNextFile`.|Kullanım [CFtpConnection::Remove](../mfc/reference/cftpconnection-class.md#remove), tarafından döndürülen dosya adını kullanarak `FindFile` veya `FindNextFile`.|Okuma veya yazma için dosya sunucusunda siler.|
|Özel durumları işler.|Kullanım [Cınternetexception](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türlerini işler.|
|FTP oturumunu sonlandırın.|Elden [Cınternetsession](../mfc/reference/cinternetsession-class.md) nesne.|Dosya tanıtıcılarını Aç ve bağlantıları tarafından otomatik olarak temizlenir.|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (WinInet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet İstemci Sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
