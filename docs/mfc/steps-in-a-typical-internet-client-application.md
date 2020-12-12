---
description: 'Daha fazla bilgi edinin: tipik bir Internet Istemci uygulamasındaki adımlar'
title: Tipik Bir Internet İstemci Uygulamasındaki Adımlar
ms.date: 11/04/2016
helpviewer_keywords:
- Internet client applications [MFC], general table
- WinInet classes [MFC], programming
- Internet applications [MFC], client applications
ms.assetid: 7aba135c-7c15-4e2f-8c34-bbaf792c89a6
ms.openlocfilehash: 9660687136361efb0256ecdd1fd19b577c46ab26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216554"
---
# <a name="steps-in-a-typical-internet-client-application"></a>Tipik Bir Internet İstemci Uygulamasındaki Adımlar

Aşağıdaki tabloda, tipik bir Internet istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.

|Amacınız|Gerçekleştirebileceğiniz eylemler|Etkiler|
|---------------|----------------------|-------------|
|Bir Internet oturumu başlatın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi oluşturun.|Winınet 'i başlatır ve sunucuya bağlanır.|
|Bir Internet sorgu seçeneği (örneğin, zaman aşımı sınırı veya yeniden deneme sayısı) ayarlayın.|[CInternetSession:: SetOption](../mfc/reference/cinternetsession-class.md#setoption)kullanın.|İşlem başarısız olursa FALSE döndürür.|
|Oturumun durumunu izlemek için bir geri çağırma işlevi oluşturun.|[CInternetSession:: EnableStatusCallback](../mfc/reference/cinternetsession-class.md#enablestatuscallback)kullanın.|[CInternetSession:: OnStatusCallback](../mfc/reference/cinternetsession-class.md#onstatuscallback)için bir geri çağırma oluşturur. `OnStatusCallback`Kendi geri arama yordamınız oluşturmak için geçersiz kılın.|
|Bir Internet sunucusuna, intranet sunucusuna veya yerel dosyaya bağlanın.|[CInternetSession:: OpenURL](../mfc/reference/cinternetsession-class.md#openurl)kullanın.|URL 'YI ayrıştırır ve belirtilen sunucuya bir bağlantı açar. Bir [CStdioFile](../mfc/reference/cstdiofile-class.md) döndürür ( `OpenURL` yerel bir dosya adı geçirirseniz). Bu, sunucu veya dosyadan alınan verilere erişebileceğiniz nesnedir.|
|Dosyadan okuyun.|[CInternetFile:: Read](../mfc/reference/cinternetfile-class.md#read)kullanın.|Sağladığınız arabelleği kullanarak belirtilen sayıda bayt okur.|
|Özel durumları işleyin.|[CInternetException](../mfc/reference/cinternetexception-class.md) sınıfını kullanın.|Tüm ortak Internet özel durum türlerini işler.|
|Internet oturumunu sonlandırın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi atılamadı.|Açık dosya tutamaçlarını ve bağlantıları otomatik olarak temizler.|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet Istemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinINet sınıfları kullanarak Internet Istemci uygulaması yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
