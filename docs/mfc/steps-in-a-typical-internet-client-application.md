---
title: "Tipik Internet istemci uygulamasında adımlar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ce4f5b91ebd68f13510f887c65927dbe5f84133
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="steps-in-a-typical-internet-client-application"></a>Tipik Bir Internet İstemci Uygulamasındaki Adımlar
Aşağıdaki tabloda, tipik bir Internet istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.  
  
|Amacınız|Eylemleri|Etkiler|  
|---------------|----------------------|-------------|  
|Bir Internet oturumu başlayın.|Oluşturma bir [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|WinINet başlatır ve sunucusuna bağlanır.|  
|Bir Internet sorgu seçeneği (zaman aşımı sınırı veya örnek için yeniden deneme sayısı) olarak ayarlayın.|Kullanım [CInternetSession::SetOption](../mfc/reference/cinternetsession-class.md#setoption).|İşlem başarısız olursa FALSE döndürür.|  
|Oturum durumunu izlemek için bir geri çağırma işlevini oluşturun.|Kullanım [CInternetSession::EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback).|Bir geri çağırma oluşturur [CInternetSession::OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback). Geçersiz kılma `OnStatusCallback` kendi geri arama yordamı oluşturmak için.|  
|Bir Internet sunucusu, intranet sunucusu veya yerel dosya bağlayın.|Kullanım [CInternetSession::OpenURL](../mfc/reference/cinternetsession-class.md#openurl).|URL ayrıştırır ve belirtilen sunucu bir bağlantı açar. Döndürür bir [CStdioFile](../mfc/reference/cstdiofile-class.md) (geçirirseniz `OpenURL` bir yerel dosya adı). Bu sunucu veya dosyasından alınan veri erişim nesnesidir.|  
|Dosyadan okuma.|Kullanım [CInternetFile::Read](../mfc/reference/cinternetfile-class.md#read).|Belirtilen sayıda baytı bir arabellek sağladığınız kullanarak okur.|  
|Özel durumları işleme.|Kullanım [CInternetException](../mfc/reference/cinternetexception-class.md) sınıfı.|Tüm ortak Internet özel durum türleri işler.|  
|Internet oturumunu sonlandırın.|Elden [CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi.|Otomatik olarak açık dosya tanıtıcıları ve bağlantıları temizler.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Win32 Internet Uzantıları (WinINet)](../mfc/win32-internet-extensions-wininet.md)   
 [Internet İstemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)   
 [MFC WinInet Sınıfları Kullanarak Internet İstemci Uygulaması Yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
