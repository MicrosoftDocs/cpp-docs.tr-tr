---
title: Visual Studio'da yeni bir C++ Linux projesi oluşturma
ms.date: 06/07/2019
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: e39e60c906901420a4809c22b4f4e71d3b621da1
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821647"
---
# <a name="create-a-new-linux-project"></a>Yeni Linux projesi oluşturma

::: moniker range="vs-2015"

Linux projeleri, Visual Studio 2017 ile kullanılabilir ve üzeri.

::: moniker-end

İlk olarak, sahip olduğunuzdan emin olun **Linux geliştirme iş yükü** yüklü Visual Studio için. Daha fazla bilgi için [indirin, yükleyin ve Linux iş yükünü Kurulum](download-install-and-setup-the-linux-development-workload.md).

Yeni bir oluşturduğunuzda C++ proje Visual Studio'da Linux için Visual Studio projesi ya da bir CMake projesini oluşturmayı seçebilirsiniz. Bu makalede, Visual Studio projesi oluşturma işlemini açıklar. Oluşturma ve mevcut CMake projelerini ile çalışma hakkında daha fazla bilgi için bkz. [Linux CMake projesi yapılandırma ](cmake-linux-project.md).

## <a name="to-create-a-new-linux-project"></a>Yeni Linux projesi oluşturmak için

Visual Studio'da yeni Linux projesi oluşturmak için aşağıdaki adımları izleyin:

::: moniker range="vs-2019"

1. Seçin **Dosya > Yeni proje** Visual Studio'da ya da tuşuna **Ctrl + Shift + N**.
1. Ayarlama **dil** için **C++** ve "Linux" arayın. Oluşturun ve ardından Proje türünü seçin **sonraki**. Girin bir **adı** ve **konumu**ve **Oluştur**.

   ![Yeni Linux projesi](media/newproject-vs2019.png)

::: moniker-end

::: moniker range="vs-2017"

1. Seçin **Dosya > Yeni proje** Visual Studio'da ya da tuşuna **Ctrl + Shift + N**.
1. Seçin **Visual C++ > Çoklu Platform > Linux** düğüm ve oluşturulacak proje türünü seçin. Girin bir **adı** ve **konumu**ve **Tamam**.

   ![Yeni Linux projesi](media/newproject.png)

::: moniker-end

   | Proje türü | Açıklama |
   | ------------ | --- |
   | **Yanıp sönme (Raspberry)**           | Bir LED'i yanıp örnek kod ile Raspberry Pi yer alan bir cihaz için hedeflenen bir proje |
   | **Konsol uygulaması (Linux)** | Konsola metni çıkardığından örnek kod ile herhangi bir Linux bilgisayar için hedeflenen bir proje |
   | **Boş proje (Linux)**       | Örnek kod olmadan herhangi bir Linux bilgisayar için hedeflenen bir proje |
   | **Derleme görevleri dosyası projesi (Linux)**    | Derleme Sistemi standart bir derleme görevleri dosyası kullanılarak oluşturulan tüm Linux bilgisayar için hedeflenen bir proje |

## <a name="next-steps"></a>Sonraki Adımlar

[Linux projesi yapılandırma](configure-a-linux-project.md)
