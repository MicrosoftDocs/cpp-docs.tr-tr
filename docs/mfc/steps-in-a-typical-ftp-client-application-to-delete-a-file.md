---
title: "Bir dosyayı silmek için tipik bir FTP istemci uygulamasında adımlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Internet client applications [MFC], FTP delete
- WinInet classes [MFC], FTP
- FTP (File Transfer Protocol) [MFC], client applications
- Internet applications [MFC], FTP client applications
ms.assetid: 2c347a96-c0a4-4827-98fe-668406e552bc
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d9da0db842267e12f9697f2416783286300b84b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="steps-in-a-typical-ftp-client-application-to-delete-a-file"></a>Dosya Silmek için Tipik Bir FTP İstemci Uygulamasındaki Adımlar
Aşağıdaki tabloda, bir dosya sildiğinde bir tipik FTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.  
  
|Amacınız|Eylemleri|Etkiler|  
|---------------|----------------------|-------------|  
|Bir FTP oturumunun başlayın.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|WinINet başlatır ve sunucusuna bağlanır.|  
|Bir FTP sunucusuna bağlanın.|Kullanım [CInternetSession::GetFtpConnection](../mfc/reference/cinternetsession-class.md#getftpconnection).|Döndürür bir [CFtpConnection](../mfc/reference/cftpconnection-class.md) nesnesi.|  
|FTP sunucusunda doğru dizinde olduğunuzdan emin olmak için kontrol edin.|Kullanım [CFtpConnection::GetCurrentDirectory](../mfc/reference/cftpconnection-class.md#getcurrentdirectory) veya [CFtpConnection::GetCurrentDirectoryAsURL](../mfc/reference/cftpconnection-class.md#getcurrentdirectoryasurl).|Adı veya şu anda seçili üye işlevi bağlı olarak sunucuya bağlı dizininin URL'sini döndürür.|  
|Sunucuda yeni bir FTP dizinine geçin.|Kullanım [CFtpConnection::SetCurrentDirectory](../mfc/reference/cftpconnection-class.md#setcurrentdirectory).|Şu anda sunucu üzerinde bağlı dizini değiştirir.|  
|İlk dosya FTP dizinde bulun.|Kullanım [CFtpFileFind::FindFile](../mfc/reference/cftpfilefind-class.md#findfile).|İlk dosyayı bulur. Hiçbir dosya bulunamazsa FALSE döndürür.|  
|Sonraki dosyasını FTP dizinde bulun.|Kullanım [CFtpFileFind::FindNextFile](../mfc/reference/cftpfilefind-class.md#findnextfile).|Sonraki dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|  
|Tarafından bulunan dosya silme **FindFile** veya `FindNextFile`.|Kullanım [CFtpConnection::Remove](../mfc/reference/cftpconnection-class.md#remove), dosya adını kullanarak döndürülen **FindFile** veya `FindNextFile`.|Okuma veya yazma için dosya sunucusunda siler.|  
|Özel durumları işleme.|Kullanım [CInternetException](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türleri işler.|  
|FTP oturumunu sonlandırın.|Elden [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|Otomatik olarak açık dosya tanıtıcıları ve bağlantıları temizler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet İstemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinINet sınıfları kullanarak Internet istemci uygulaması yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
