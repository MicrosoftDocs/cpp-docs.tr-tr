---
title: Visual Studio 'da için C++ Live Share işbirliği yapın
description: İşbirliği yapmak ve C++ kodu gerçek zamanlı olarak paylaşmak Için Visual Studio 'da için Live Share kullanın.
ms.date: 05/24/2019
ms.openlocfilehash: e6e983c6acb56dffd12756d8bbaccef32dd57f38
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80077776"
---
# <a name="collaborate-using-live-share-for-c"></a>C++ için Live Share kullanarak işbirliği yapma

Visual Studio 2019 ve Visual Studio Code ' de, **live share** kullanarak projeler üzerinde C++ gerçek zamanlı işbirliği yapabilirsiniz. **Live share** başka bir kişi, projenizi veya bağımlılıklarından herhangi birini yüklemeye gerek kalmadan kodunuzu düzenleyebilir ve hatalarını ayıklayabilirler. Her birinin yaptığı düzenlemeleri görürsünüz ve her düzenleme bunu yapan kişinin adıyla etiketlendi.

![C&#43; &#43; Live Share düzenlemesi](../ide/media/live-share-edit-cpp.png "İçinde Live Share düzenlemesiC++")

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

![C&#43; &#43; Live Share hata ayıklama](../ide/media/live-share-debug-cpp.png "Live Share hata ayıklamaC++")

## <a name="start-and-end-a-live-share-session"></a>Live Share oturumu başlatma ve sonlandırma

Visual Studio 'da bir Live Share oturumu başlatmak için sağ üstteki paylaşma düğmesine tıklayın veya **dosya** > " **işbirliği oturumu Başlat**" a gidin. Bu, ortak çalışanlarla paylaşabileceğiniz bir bağlantı oluşturur.

![C&#43; &#43; Live Share düğmesi](../ide/media/live-share-button-cpp.png "Live Share düğmesi")

Bir oturumu sonlandırmak için, **Paylaşım** açılan menüsünden **işbirliği oturumunu Sonlandır** ' ı seçin.

![C&#43; &#43; Live Share düğmesi](../ide/media/live-share-end-session-cpp.png "Live Share düğmesi")

## <a name="for-more-information"></a>Daha fazla bilgi edinmek için

Visual Studio 'da **live share** hakkında daha fazla bilgi için bkz. [Visual Studio Live Share nedir?](/visualstudio/liveshare/). Visual Studio Code Live Share hakkında daha fazla bilgi için bkz. [live share](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare).

## <a name="see-also"></a>Ayrıca Bkz.

[Kodu düzenleme ve yeniden düzenlemeC++()](writing-and-refactoring-code-cpp.md)</br>
[Visual Studio C++ 'da kod tabanınız üzerinde gezinme](navigate-code-cpp.md)</br>
[Kodu okuyun ve C++ anlayın](read-and-understand-code-cpp.md)</br>