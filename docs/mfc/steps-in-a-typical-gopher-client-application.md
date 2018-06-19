---
title: Tipik bir Gopher istemci uygulamasında adımlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6ebb97d7cb5cbf2e2ed9ac7ae5287b2261990f2b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33381117"
---
# <a name="steps-in-a-typical-gopher-client-application"></a>Tipik Bir Gopher İstemci Uygulamasındaki Adımlar
Aşağıdaki tabloda, tipik bir gopher istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.  
  
|Amacınız|Eylemleri|Etkiler|  
|---------------|----------------------|-------------|  
|Gopher oturum başlar.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|WinINet başlatır ve sunucusuna bağlanır.|  
|Gopher sunucuya bağlanın.|Kullanım [CInternetSession::GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection).|Döndürür bir [CGopherConnection](../mfc/reference/cgopherconnection-class.md) nesnesi.|  
|İlk kaynak gopher bulun.|Kullanım [CGopherFileFind::FindFile](../mfc/reference/cgopherfilefind-class.md#findfile).|İlk dosyayı bulur. Hiçbir dosya bulunamazsa FALSE döndürür.|  
|Sonraki kaynak gopher bulun.|Kullanım [CGopherFileFind::FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile).|Sonraki dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|  
|Tarafından bulunan dosya açmak **FindFile** veya `FindNextFile` okumak için.|Kullanarak bir gopher Bulucu alma [CGopherFileFind::GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator). Kullanım [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Bulucu tarafından belirtilen dosyayı açar. `OpenFile` döndüren bir [CGopherFile](../mfc/reference/cgopherfile-class.md) nesnesi.|  
|Sağladığınız bir gopher Bulucu kullanarak bir dosyayı açın.|Kullanarak bir gopher Bulucu oluşturmanız [CGopherConnection::CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator). Kullanım [CGopherConnection::OpenFile](../mfc/reference/cgopherconnection-class.md#openfile).|Bulucu tarafından belirtilen dosyayı açar. `OpenFile` döndüren bir [CGopherFile](../mfc/reference/cgopherfile-class.md) nesnesi.|  
|Dosyadan okuma.|Kullanım [CGopherFile](../mfc/reference/cgopherfile-class.md).|Belirtilen sayıda baytı, sağladığınız arabellek kullanarak okur.|  
|Özel durumları işleme.|Kullanım [CInternetException](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türleri işler.|  
|Gopher oturumunu sonlandırın.|Elden [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|Otomatik olarak açık dosya tanıtıcıları ve bağlantıları temizler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet İstemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
