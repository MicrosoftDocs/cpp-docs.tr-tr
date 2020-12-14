---
description: 'Daha fazla bilgi edinin: tipik bir Gopher Istemci uygulamasındaki adımlar'
title: Tipik Bir Gopher İstemci Uygulamasındaki Adımlar
ms.date: 11/04/2016
helpviewer_keywords:
- WinInet classes [MFC], gopher
- Internet applications [MFC], gopher client applications
- Gopher client applications [MFC]
- Internet client applications [MFC], gopher table
ms.assetid: 3e4e1869-5da0-453d-8ba9-b648c894bb90
ms.openlocfilehash: 23940457acf52009b6d334deec129324a53a7583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216632"
---
# <a name="steps-in-a-typical-gopher-client-application"></a>Tipik Bir Gopher İstemci Uygulamasındaki Adımlar

Aşağıdaki tabloda tipik bir Gopher istemci uygulamasında gerçekleştirebileceğiniz adımlar gösterilmektedir.

|Amacınız|Gerçekleştirebileceğiniz eylemler|Etkiler|
|---------------|----------------------|-------------|
|Bir gopher oturumu başlatın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi oluşturun.|Winınet 'i başlatır ve sunucuya bağlanır.|
|Gopher sunucusuna bağlanın.|[CInternetSession:: GetGopherConnection](../mfc/reference/cinternetsession-class.md#getgopherconnection)kullanın.|Bir [CGopherConnection](../mfc/reference/cgopherconnection-class.md) nesnesi döndürür.|
|Gopher içindeki ilk kaynağı bulun.|[CGopherFileFind:: FindFile](../mfc/reference/cgopherfilefind-class.md#findfile)kullanın.|İlk dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|
|Gopher içindeki bir sonraki kaynağı bulun.|[CGopherFileFind:: FindNextFile](../mfc/reference/cgopherfilefind-class.md#findnextfile)kullanın.|Sonraki dosyayı bulur. Dosya bulunamazsa FALSE döndürür.|
|`FindFile`Veya okuma için bulunan dosyayı açın `FindNextFile` .|[CGopherFileFind:: GetLocator](../mfc/reference/cgopherfilefind-class.md#getlocator)kullanarak bir Gopher Bulucu alın. [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)kullanın.|Bulucu tarafından belirtilen dosyayı açar. `OpenFile` bir [CGopherFile](../mfc/reference/cgopherfile-class.md) nesnesi döndürür.|
|Sağladığınız bir Gopher Bulucu kullanarak bir dosya açın.|[CGopherConnection:: CreateLocator](../mfc/reference/cgopherconnection-class.md#createlocator)kullanarak bir Gopher Bulucu oluşturun. [CGopherConnection:: OpenFile](../mfc/reference/cgopherconnection-class.md#openfile)kullanın.|Bulucu tarafından belirtilen dosyayı açar. `OpenFile` bir [CGopherFile](../mfc/reference/cgopherfile-class.md) nesnesi döndürür.|
|Dosyadan okuyun.|[CGopherFile](../mfc/reference/cgopherfile-class.md)kullanın.|Sağladığınız arabelleği kullanarak belirtilen sayıda bayt okur.|
|Özel durumları işleyin.|[CInternetException](../mfc/reference/cinternetexception-class.md) sınıfını kullanın.|Tüm ortak Internet özel durum türlerini işler.|
|Gopher oturumunu sonlandırın.|[CInternetSession](../mfc/reference/cinternetsession-class.md) nesnesi atılamadı.|Açık dosya tutamaçlarını ve bağlantıları otomatik olarak temizler.|

## <a name="see-also"></a>Ayrıca bkz.

[Win32 Internet Uzantıları (Winınet)](../mfc/win32-internet-extensions-wininet.md)<br/>
[Internet Istemci sınıfları için Önkoşullar](../mfc/prerequisites-for-internet-client-classes.md)<br/>
[MFC WinINet sınıfları kullanarak Internet Istemci uygulaması yazma](../mfc/writing-an-internet-client-application-using-mfc-wininet-classes.md)
