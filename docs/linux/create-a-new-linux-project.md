---
title: Visual Studio'da yeni bir C++ Linux projesi oluşturma
ms.date: 09/12/2018
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 394fc5727035dd5a65b67ebf26a925fd3484582e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623034"
---
# <a name="create-a-new-linux-project"></a>Yeni Linux projesi oluşturma

İlk olarak, sahip olduğunuzdan emin olun **Linux geliştirme iş yükü** yüklü Visual Studio için. Daha fazla bilgi için [indirin, yükleyin ve Linux iş yükünü Kurulum](download-install-and-setup-the-linux-development-workload.md).

Linux için Visual Studio'da yeni bir C++ projesi oluştururken, Visual Studio projesi ya da bir CMake projesini oluşturma seçeneğiniz vardır. Bu konuda, Visual Studio projesi oluşturma işlemini açıklar. Oluşturma ve mevcut CMake projelerini ile çalışma hakkında daha fazla bilgi için bkz: [Linux CMake projesi yapılandırma ](cmake-linux-project.md).

Visual Studio'da yeni Linux projesi oluşturmak için aşağıdakileri yapın:

1. Seçin **Dosya > Yeni proje** Visual Studio'da ya da tuşuna **Ctrl + Shift + N**.
1. Seçin **Visual C++ > Çoklu Platform > Linux** düğümünü ve ardından oluşturmak istediğiniz proje türü adı/konum girin ve Tamam'a tıklayın.

   ![Yeni Linux projesi](media/newproject.png)

   | Proje türü | Açıklama
   | ------------ | ---
   | **Yanıp sönme (Raspberry)**           | Raspberry Pi'yi cihaz için bir yanıp sönme yazılan örnek kod ile hedeflenen proje
   | **Konsol uygulaması (Linux)** | Proje metin konsola çıktı olarak yazılan örnek kod ile herhangi bir Linux bilgisayar için hedeflenmiş
   | **Boş proje (Linux)**       | Örnek kod olmadan yazılan herhangi bir Linux bilgisayar için hedeflenen bir proje
   | **Derleme görevleri dosyası projesi (Linux)**    | Derleme sistemi, standart bir derleme görevleri dosyası kullanılarak oluşturulan Linux bilgisayar için hedeflenen bir proje

