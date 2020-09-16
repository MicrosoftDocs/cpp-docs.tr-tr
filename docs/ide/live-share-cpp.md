---
title: Visual Studio 'da C++ için Live Share işbirliği yapın
description: İşbirliği yapmak ve kodu gerçek zamanlı olarak paylaşmak için Visual Studio 'da C++ için Live Share kullanın.
ms.date: 05/24/2019
ms.openlocfilehash: 60830ad6c6b98f644e1c3ddb2e78fbf7397ae919
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684527"
---
# <a name="collaborate-using-live-share-for-c"></a>C++ için Live Share kullanarak işbirliği yapma

Visual Studio 2019 ve Visual Studio Code 'de, C++ projelerinde gerçek zamanlı olarak işbirliği yapmak için **live share** kullanabilirsiniz. **Live share** başka bir kişi, projenizi veya bağımlılıklarından herhangi birini yüklemeye gerek kalmadan kodunuzu düzenleyebilir ve hatalarını ayıklayabilirler. Her birinin yaptığı düzenlemeleri görürsünüz ve her düzenleme bunu yapan kişinin adıyla etiketlendi.

![C&#43;&#43; Live Share Düzenle](../ide/media/live-share-edit-cpp.png "C++ ' ta Live Share düzenlemesi")

## <a name="live-share-host-and-guests"></a>Live Share Konağı ve konukları

Live Share oturumunda bir konak ve bir veya daha fazla konuk vardır. Hem ana bilgisayar hem de konuklar, Visual Studio veya Visual Studio Code kullanabilir. Windows üzerinde bir Visual Studio 2019 Konağı, Linux üzerinde Visual Studio Code konuğiyle paylaşabilir.

Konak, konuklara üretken olmaları gereken her şeyi sağlar. Konukların kaynak kodu, derleyici, dış bağımlılıklar ve hatta aynı yüklü bileşenleri olması gerekmez.

Konak ve konuklar şu IntelliSense özelliklerini kullanabilir:

- Üye listesi
- Parametre yardımı
- Hızlı Bilgi
- Hata ayıklama/kesme noktaları
- Tüm Başvuruları Bul
- Tanıma Git
- Sembol arama (Ctrl + T)
- Başvuru vurgulama
- Tanılama/hatalar/dalgalı çizgiler

![C&#43;&#43; Live Share hata ayıklama](../ide/media/live-share-debug-cpp.png "C++ ' da hata ayıklamayı Live Share")

## <a name="start-and-end-a-live-share-session"></a>Live Share oturumu başlatma ve sonlandırma

Visual Studio 'da bir Live Share oturumu başlatmak için sağ üst köşedeki paylaşma düğmesine tıklayın veya **dosyayı**  >  **Başlat işbirliği oturumuna**gidin. Bu, ortak çalışanlarla paylaşabileceğiniz bir bağlantı oluşturur.

![Live Share düğmesinin küçük bir ekran görüntüsü.](../ide/media/live-share-button-cpp.png "Live Share düğmesi")

Bir oturumu sonlandırmak için, **Paylaşım** açılan menüsünden **işbirliği oturumunu Sonlandır** ' ı seçin.

![Son Işbirliği oturumu seçeneği vurgulanmış şekilde paylaşım açılan listesinin ekran görüntüsü.](../ide/media/live-share-end-session-cpp.png "Live Share düğmesi")

## <a name="for-more-information"></a>Daha fazla bilgi edinmek için

Visual Studio 'da **live share** hakkında daha fazla bilgi için bkz. [Visual Studio Live Share nedir?](/visualstudio/liveshare/). Visual Studio Code Live Share hakkında daha fazla bilgi için bkz. [ live share](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare).

## <a name="see-also"></a>Ayrıca Bkz.

[Kodu düzenleme ve yeniden düzenleme (C++)](writing-and-refactoring-code-cpp.md)</br>
[Visual Studio 'da C++ kod tabanınız üzerinde gezinme](navigate-code-cpp.md)</br>
[C++ kodunu okuma ve anlama](read-and-understand-code-cpp.md)</br>
