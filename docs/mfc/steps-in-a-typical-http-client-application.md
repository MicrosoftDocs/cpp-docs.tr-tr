---
description: 'Daha fazla bilgi edinin: tipik bir HTTP Istemci uygulamasındaki adımlar'
title: Tipik Bir HTTP İstemci Uygulamasındaki Adımlar
ms.date: 11/04/2016
helpviewer_keywords:
- HTTP client applications [MFC]
- client applications [MFC], HTTP
- Internet applications [MFC], HTTP client applications
- applications [MFC], HTTP client
- Internet client applications [MFC], HTTP table
- WinInet classes [MFC], HTTP
ms.assetid: f86552e8-8acd-4b23-bdc5-0c3a247ebd74
ms.openlocfilehash: 0f08ca7629c389df67b579b8c20acceeb16b0cd3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216606"
---
# <a name="steps-in-a-typical-http-client-application"></a>Tipik Bir HTTP İstemci Uygulamasındaki Adımlar

Aşağıdaki tabloda, tipik bir HTTP istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir:

|Amacınız|Gerçekleştirebileceğiniz eylemler|Etkiler|
|---------------|----------------------|-------------|
|Bir HTTP oturumu başlatın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi oluşturun.|Winınet 'i başlatır ve sunucuya bağlanır.|
|Bir HTTP sunucusuna bağlanın.|[CInternetSession:: GetHttpConnection](../mfc/reference/cinternetsession-class.md#gethttpconnection)kullanın.|Bir [CHttpConnection](../mfc/reference/chttpconnection-class.md) nesnesi döndürür.|
|Bir HTTP isteği açın.|[CHttpConnection:: OpenRequest](../mfc/reference/chttpconnection-class.md#openrequest)kullanın.|Bir [CHttpFile](../mfc/reference/chttpfile-class.md) nesnesi döndürür.|
|HTTP isteği gönderin.|[CHttpFile:: AddRequestHeaders](../mfc/reference/chttpfile-class.md#addrequestheaders) ve [CHttpFile:: SendRequest](../mfc/reference/chttpfile-class.md#sendrequest)kullanın.|Dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|
|Dosyadan okuyun.|[CHttpFile](../mfc/reference/chttpfile-class.md)kullanın.|Sağladığınız arabelleği kullanarak belirtilen sayıda bayt okur.|
|Özel durumları işleyin.|[CInternetException](../mfc/reference/cinternetexception-class.md) sınıfını kullanın.|Tüm ortak Internet özel durum türlerini işler.|
|HTTP oturumunu sonlandırın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi atılamadı.|Açık dosya tutamaçlarını ve bağlantıları otomatik olarak temizler.|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet Istemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinINet sınıfları kullanarak Internet Istemci uygulaması yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
