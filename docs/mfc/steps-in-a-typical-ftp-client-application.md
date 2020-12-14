---
description: 'Daha fazla bilgi edinin: tipik bir FTP Istemci uygulamasındaki adımlar'
title: Tipik Bir FTP İstemci Uygulamasındaki Adımlar
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], FTP table
- FTP (File Transfer Protocol)
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 70bed7b5-6040-40d1-bc77-702e63a698f2
ms.openlocfilehash: caac613adf3ad886c4b36ae567a3b8c5c928ee10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216645"
---
# <a name="steps-in-a-typical-ftp-client-application"></a>Tipik Bir FTP İstemci Uygulamasındaki Adımlar

Tipik bir FTP istemci uygulaması, bir [Cınternetoturumu](../mfc/reference/cinternetsession-class.md) ve bir [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesnesi oluşturur. Bu MFC WinInet sınıflarının proxy türü ayarlarını gerçekten denetlemeyeceğini unutmayın; IIS.

Aşağıdaki tabloda tipik bir FTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.

|Amacınız|Gerçekleştirebileceğiniz eylemler|Etkiler|
|---------------|----------------------|-------------|
|Bir FTP oturumu başlatın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi oluşturun.|Winınet 'i başlatır ve sunucuya bağlanır.|
|Bir FTP sunucusuna bağlanın.|[CInternetSession:: GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection)kullanın.|[CFtpConnection](../mfc/reference/cftpconnection-class.md) nesnesini döndürür.|
|Sunucusunda yeni bir FTP dizinine geçin.|[CFtpConnection:: SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory)kullanın.|Sunucuda şu anda bağlı olduğunuz dizini değiştirir.|
|FTP dizinindeki ilk dosyayı bulun.|[CFtpFileFind:: FindFile](../mfc/reference/cftpfilefind-class.md#findfile)kullanın.|İlk dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|
|FTP dizininde bir sonraki dosyayı bulun.|[CFtpFileFind:: FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)kullanın.|Sonraki dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|
|`FindFile`Veya `FindNextFile` okuma ya da yazma için bulunan dosyayı açın.|[FindFile](../mfc/reference/cftpfilefind-class.md#findfile) veya [FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile)tarafından döndürülen dosya adını kullanarak [CFtpConnection:: OpenFile](../mfc/reference/cftpconnection-class.md#openfile)kullanın.|Dosyayı okumak veya yazmak için sunucuda açar. Bir [CInternetFile](../mfc/reference/cinternetfile-class.md) nesnesi döndürür.|
|Dosyadan okuma veya yazma.|[CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read) veya [CInternetFile:: Write](../mfc/reference/cinternetfile-class.md#write)kullanın.|Sağladığınız arabelleği kullanarak belirtilen sayıda bayt okur veya yazar.|
|Özel durumları işleyin.|[CInternetException](../mfc/reference/cinternetexception-class.md) sınıfını kullanın.|Tüm ortak Internet özel durum türlerini işler.|
|FTP oturumunu sonlandırın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi atılamadı.|Açık dosya tutamaçlarını ve bağlantıları otomatik olarak temizler.|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet Istemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinINet sınıfları kullanarak Internet Istemci uygulaması yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
