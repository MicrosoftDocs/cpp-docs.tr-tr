---
title: Canlı paylaşım için işbirliği C++ Visual Studio'da
description: Canlı paylaşmak için kullanma C++ gerçek zamanlı olarak kod paylaşın ve işbirliği yapmak için Visual Studio'da.
ms.date: 05/24/2019
ms.openlocfilehash: 8886bb3ea4b7389a9d6953655e2dc6ccfa1c7c9a
ms.sourcegitcommit: 65ed563a8a1d4d90f872a2a6edcb086f84ec9f77
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66743395"
---
# <a name="collaborate-using-live-share-for-c"></a>Live Share'ı kullanarak işbirliği yapmaC++

Visual Studio 2019 ve Visual Studio Code, kullanabileceğiniz **Live Share** üzerinde işbirliği yapmak için C++ gerçek zamanlı projeleri. İle **Live Share** başka bir kişiye düzenleyebilir ve projeniz veya bağımlılıklarından biri yüklemeye gerek kalmadan kodunuzu hata ayıklama. Diğer kişilerin düzenlemeleri ortaya ve her Düzen bunu yapan kişinin adı ile etiketlenmiş bakın. 

![C&#43; &#43; Canlı Paylaşım düzenleme](../ide/media/live-share-edit-cpp.png "paylaşımı düzenleme Live'daC++")

## <a name="live-share-host-and-guests"></a>Canlı Paylaşım konak ve Konuk

LiveShare oturumuna içinde bir ana bilgisayar ve bir veya daha fazla Konukları yoktur. Hem konak hem de Konuklar, Visual Studio veya Visual Studio Code kullanabilirsiniz. Bir Visual Studio 2019 ana bilgisayarda Windows, Linux üzerinde Visual Studio Code Konuk ile paylaşabilirsiniz.

Konağın Konuk üretken olmak için ihtiyaç duydukları her şeyi içeren sağlar. Konuklar kaynak kodu, derleyici, dış bağımlılıklar sağlamak için gerekli değildir veya hatta aynı bileşenler yüklü. 

Konuk ve konak şu IntelliSense özellikleri kullanabilir: 

- Üye listesi
- Parametre Yardımı
- Hızlı Bilgi
- Hata ayıklama/kesme noktaları
- Tüm Başvuruları Bul
- Tanıma Git
- Sembol arama (Ctrl + T)
- Başvuru vurgulama
- Tanılama/hatalar/dalgalı çizgiler

![C&#43; &#43; paylaşımı hata ayıklama canlı](../ide/media/live-share-debug-cpp.png "paylaşımı hata ayıklama Live'daC++")

## <a name="start-and-end-a-live-share-session"></a>Başlangıç ve bitiş LiveShare oturumuna

Visual Studio'da LiveShare oturumuna başlamak için sağ üst köşesindeki Paylaş düğmesini tıklatın veya Git **dosya** > **işbirliği oturumu Başlat**. Bu, ortak çalışanlarla paylaşabileceğiniz bir bağlantı oluşturur.

![C&#43; &#43; Canlı Paylaşım düğmesi](../ide/media/live-share-button-cpp.png "Canlı Paylaşım düğmesi")

Bir oturumunu sona erdirmek için seçin **işbirliği oturumu sonlandır** gelen **paylaşım** açılır.

![C&#43; &#43; Canlı Paylaşım düğmesi](../ide/media/live-share-end-session-cpp.png "Canlı Paylaşım düğmesi")

## <a name="for-more-information"></a>Daha fazla bilgi için

Hakkında daha fazla bilgi için **Live Share** Visual Studio'da görmek [Visual Studio Live Share nedir?](/visualstudio/liveshare/). Visual Studio code'da Live Share hakkında daha fazla bilgi için bkz: [ Live Share](https://marketplace.visualstudio.com/items?itemName=ms-vsliveshare.vsliveshare).

## <a name="see-also"></a>Ayrıca Bkz.

[Düzenleme ve yeniden düzenleme, kod (C++)](writing-and-refactoring-code-cpp.md)</br>
[Git, C++ Visual Studio'da temel kod](navigate-code-cpp.md)</br>
[Okumanız ve anlamanız C++ kod](read-and-understand-code-cpp.md)</br>