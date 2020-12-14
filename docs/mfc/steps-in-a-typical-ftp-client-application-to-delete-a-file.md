---
description: 'Hakkında daha fazla bilgi edinin: bir dosyayı silmek için tipik bir FTP Istemci uygulamasındaki adımlar'
title: Dosya Silmek için Tipik Bir FTP İstemci Uygulamasındaki Adımlar
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
ms.openlocfilehash: 0de5ba71ac127a44c964571d243997bcb49faaa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216658"
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Dosya Silmek için Tipik Bir FTP İstemci Uygulamasındaki Adımlar

Aşağıdaki tabloda, bir dosyayı silen tipik bir FTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.

|Amacınız|Gerçekleştirebileceğiniz eylemler|Etkiler|
|---------------|----------------------|-------------|
|Bir FTP oturumu başlatın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi oluşturun.|Winınet 'i başlatır ve sunucuya bağlanır.|
|Bir FTP sunucusuna bağlanın.|[CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)kullanın.|[CFtpConnection](../mfc/reference/cftpconnection-class.md) nesnesini döndürür.|
|FTP sunucusunda doğru dizinde olduğunuzdan emin olun.|[CFtpConnection:: GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) veya [CFtpConnection:: GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl)kullanın.|Seçili üye işlevine bağlı olarak, sunucuda şu anda bağlı olduğunuz dizinin adını veya URL 'sini döndürür.|
|Sunucusunda yeni bir FTP dizinine geçin.|[CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)kullanın.|Sunucuda şu anda bağlı olduğunuz dizini değiştirir.|
|FTP dizinindeki ilk dosyayı bulun.|[CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile)kullanın.|İlk dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|
|FTP dizininde bir sonraki dosyayı bulun.|[CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)kullanın.|Sonraki dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|
|Veya tarafından bulunan dosyayı silin `FindFile` `FindNextFile` .|Veya tarafından döndürülen dosya adını kullanarak [CFtpConnection:: Remove](../mfc/reference/cftpconnection-class.md#remove)kullanın `FindFile` `FindNextFile` .|Okuma veya yazma için sunucudaki dosyayı siler.|
|Özel durumları işleyin.|[CInternetException](../mfc/reference/cinternetexception-class.md) sınıfını kullanın.|Tüm ortak Internet özel durum türlerini işler.|
|FTP oturumunu sonlandırın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi atılamadı.|Açık dosya tutamaçlarını ve bağlantıları otomatik olarak temizler.|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet Istemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinINet sınıfları kullanarak Internet Istemci uygulaması yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
