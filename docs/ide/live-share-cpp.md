---
title: Visual Studio'da C++ için Live Share ile işbirliği yapın
description: Visual Studio'da C++ için Live Share'i kullanarak gerçek zamanlı olarak işbirliği yapın ve kodu paylaşın.
ms.date: 05/24/2019
ms.openlocfilehash: 0ebdd77d0e277778b48cf69024b24841f775d968
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377281"
---
# <a name="collaborate-using-live-share-for-c"></a>C++ için Live Share kullanarak işbirliği yapma

Visual Studio 2019 ve Visual Studio Code'da, C++ projelerinde gerçek zamanlı olarak işbirliği yapmak için **Live Share'i** kullanabilirsiniz. **Live Share** ile başka bir kişi, projenizi veya bağımlılıklarından herhangi birini yüklemenize gerek kalmadan kodunuzu dinleyebilir ve hata ayıklayabilir. Birbirinin edindiklerini oluştukları gibi görürsünüz ve her bir ediyi yapan kişinin adı ile etiketlenir.

![C&#43;&#43; Canlı Paylaşım Düzenleme](../ide/media/live-share-edit-cpp.png "C++'da Canlı Paylaşım Düzenlemesi")

## <a name="live-share-host-and-guests"></a>Canlı Paylaş ev sahibi ve misafirler

Canlı Paylaşım oturumunda bir ev sahibi ve bir veya daha fazla konuk vardır. Hem ev sahibi hem de konuklar Visual Studio veya Visual Studio Code'u kullanabilirler. Windows'daki Visual Studio 2019 ev sahibi, Linux'taki Visual Studio Code konuklarıyla paylaşabilir.

Ev sahibi konuklara üretken olmaları için ihtiyaç duydukları her şeyi sağlar. Konukların kaynak koduna, derleyiciye, dış adadaklara ve hatta aynı yüklü bileşenlere sahip olması gerekmez.

Ev sahibi ve konuklar bu IntelliSense özelliklerini kullanabilir:

- Üye Listesi
- Parametre Yardımı
- Hızlı Bilgi
- Hata Ayıklama/Kesme Noktaları
- Tüm Başvuruları Bul
- Tanıma Git
- Sembol Arama (Ctrl+T)
- Referans Vurgulama
- Tanılama/Hatalar/Dalgalı

![C&#43;&#43; Canlı Paylaşım Hata Ayıklama](../ide/media/live-share-debug-cpp.png "C++'da Canlı Paylaşım Hata Ayıklama")

## <a name="start-and-end-a-live-share-session"></a>Canlı Paylaşım oturumunu başlat Ve sonla

Visual Studio'da Canlı Paylaşım oturumu başlatmak için sağ üstteki Paylaş düğmesini tıklatın veya **Dosya** > **Başlangıç İşbirliği Oturumu'na**gidin. Bu, ortak çalışanlarınızla paylaşabileceğiniz bir bağlantı oluşturur.

![C&#43;&#43; Canlı Paylaşım Düğmesi](../ide/media/live-share-button-cpp.png "Canlı Paylaşım Düğmesi")

Oturumu sonlamak için Paylaşım **açılır** tarihinden **İşbirliği oturumunu** sonla'yı seçin.

![C&#43;&#43; Canlı Paylaşım Düğmesi](../ide/media/live-share-end-session-cpp.png "Canlı Paylaşım Düğmesi")

## <a name="for-more-information"></a>Daha fazla bilgi edinmek için

Visual Studio **Live Share** hakkında daha fazla bilgi için Visual [Studio Live Share nedir?](/visualstudio/liveshare/) Visual Studio Code'da Live Share hakkında daha fazla bilgi için [Live Share'e](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare)bakın.

## <a name="see-also"></a>Ayrıca Bkz.

[Düzenleme ve yeniden düzenleme kodu (C++)](writing-and-refactoring-code-cpp.md)</br>
[Visual Studio'da C++ kod tabanınızda gezinme](navigate-code-cpp.md)</br>
[C++ kodunu okuma ve anlama](read-and-understand-code-cpp.md)</br>
