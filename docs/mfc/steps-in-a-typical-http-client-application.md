---
title: Tipik bir HTTP istemci uygulamasında adımlar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c25402662296a9ebf2f15fe902dcefabb9d47073
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33380964"
---
# <a name="steps-in-a-typical-http-client-application"></a>Tipik Bir HTTP İstemci Uygulamasındaki Adımlar
Aşağıdaki tabloda, tipik bir HTTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir:  
  
|Amacınız|Eylemleri|Etkiler|  
|---------------|----------------------|-------------|  
|Bir HTTP oturumu başlayın.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|WinINet başlatır ve sunucusuna bağlanır.|  
|Bir HTTP sunucusuna bağlanın.|Kullanım [CInternetSession::GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection).|Döndürür bir [CHttpConnection](../mfc/reference/chttpconnection-class.md) nesnesi.|  
|Bir HTTP isteği'ni açın.|Kullanım [CHttpConnection::OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest).|Döndürür bir [CHttpFile](../mfc/reference/chttpfile-class.md) nesnesi.|  
|Bir HTTP isteği gönder.|Kullanım [CHttpFile::AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) ve [CHttpFile::SendRequest](../mfc/reference/chttpfile-class.md#sendrequest).|Dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|  
|Dosyadan okuma.|Kullanım [CHttpFile](../mfc/reference/chttpfile-class.md).|Belirtilen sayıda baytı bir arabellek sağladığınız kullanarak okur.|  
|Özel durumları işleme.|Kullanım [CInternetException](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türleri işler.|  
|HTTP oturumunu sonlandırın.|Elden [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|Otomatik olarak açık dosya tanıtıcıları ve bağlantıları temizler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet İstemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
