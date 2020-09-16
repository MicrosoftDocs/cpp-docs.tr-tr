---
title: Visual Studio 'da Linux MSBuild C++ projesi oluşturma
ms.date: 08/04/2020
description: Visual Studio 'da yeni bir MSBuild tabanlı Linux projesi oluşturun.
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 559a868ebdea7e3b835a82c31849d0e2fdeaa6c9
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686697"
---
# <a name="create-a-linux-msbuild-c-project-in-visual-studio"></a>Visual Studio 'da Linux MSBuild C++ projesi oluşturma

::: moniker range="vs-2015"

Linux projeleri Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range="vs-2017"

İlk olarak, Visual Studio için **Linux geliştirme Iş yükünüzün** yüklü olduğundan emin olun. Daha fazla bilgi için bkz. [Linux iş yükünü indirme, yükleme ve kurma](download-install-and-setup-the-linux-development-workload.md).

Platformlar arası derleme için CMake kullanmanızı öneririz. CMake desteği, Visual Studio 2019 ' de daha tamamlanmıştır. CMake bir seçenek değilse ve Linux için derlemek üzere genişletmek istediğiniz mevcut bir Windows Visual Studio çözümünüz varsa, **Paylaşılan öğeler** projesiyle birlikte Windows çözümüne bir Visual Studio Linux projesi ekleyebilirsiniz. Paylaşılan öğeler projesindeki her iki platform arasında paylaşılan kodu koyun ve Windows ve Linux projelerinden bu projeye bir başvuru ekleyin.

## <a name="to-create-a-new-linux-project"></a>Yeni bir Linux projesi oluşturmak için

Visual Studio 2017 ' de yeni bir Linux projesi oluşturmak için aşağıdaki adımları izleyin:

1. Visual Studio 'da **dosya > yeni proje** ' yi seçin veya **CTRL + SHIFT + N**tuşlarına basın.
1. **Visual C++ > platformlar arası > Linux** düğümünü seçin ve ardından oluşturulacak proje türünü seçin. Bir **ad** ve **konum**girin ve **Tamam**' ı seçin.

   ![Visual C Plus ile yeni proje iletişim kutusunu gösteren ekran görüntüsü ve > platformlar arası > Linux seçili, tüm proje türleri dışarı ve adı ve konum metin kutuları de çağrılır.](media/newproject.png)

   | Proje türü | Description |
   | ------------ | --- |
   | **Yanıp sönme (Raspberry)**           | Bir Raspberry PI cihazı için hedeflenen ve bir LED 'in yanıp sönmesini sağlayan örnek kod içeren proje |
   | **Konsol uygulaması (Linux)** | Bir Linux bilgisayar için hedeflenen ve metni konsola veren örnek kod içeren proje |
   | **Boş proje (Linux)**       | Örnek kod olmadan herhangi bir Linux bilgisayar için hedeflenen proje |
   | **Makefile projesi (Linux)**    | Standart makefile derleme sistemi kullanılarak oluşturulan tüm Linux bilgisayarları için hedeflenen proje |

## <a name="next-steps"></a>Sonraki adımlar

[MSBuild Linux projesi yapılandırma](configure-a-linux-project.md)

::: moniker-end

::: moniker range="vs-2019"

İlk olarak, Visual Studio için **Linux geliştirme Iş yükünüzün** yüklü olduğundan emin olun. Daha fazla bilgi için bkz. [Linux iş yükünü indirme, yükleme ve ayarlama](download-install-and-setup-the-linux-development-workload.md).

Visual Studio 'da Linux için yeni bir C++ projesi oluşturduğunuzda, bir Visual Studio projesi veya CMake projesi oluşturmayı seçebilirsiniz. Bu makalede, Visual Studio projesinin nasıl oluşturulacağı açıklanır. Genel olarak, açık kaynak kodu içerebilen veya platformlar arası geliştirme için derlemeyi planladığınız yeni projeler için CMake 'i Visual Studio ile kullanmanızı öneririz. CMake projesi ile hem Windows hem de Linux 'ta aynı projeyi oluşturabilir ve hata ayıklayabilirsiniz. Daha fazla bilgi için bkz. [Linux CMake projesi oluşturma ve yapılandırma](cmake-linux-project.md).

Linux için derlemek üzere genişletmek istediğiniz mevcut bir Windows Visual Studio çözümünüz varsa ve CMake bir seçenek değilse, Windows çözümüne, **Paylaşılan öğeler** projesiyle birlikte bir Visual Studio Linux projesi ekleyebilirsiniz. Paylaşılan öğeler projesindeki her iki platform arasında paylaşılan kodu koyun ve Windows ve Linux projelerinden bu projeye bir başvuru ekleyin.

## <a name="to-create-a-new-linux-project"></a>Yeni bir Linux projesi oluşturmak için

Visual Studio 2019 ' de yeni bir Linux projesi oluşturmak için aşağıdaki adımları izleyin:

1. Visual Studio 'da **dosya > yeni proje** ' yi seçin veya **CTRL + SHIFT + N**tuşlarına basın.
1. **Dili** **C++** olarak ayarlayın ve "Linux" araması yapın. Oluşturulacak proje türünü seçin ve ardından **İleri**' yi seçin. Bir **ad** ve **konum**girin ve **Oluştur**' u seçin.

   ![Arama metin kutusuna, Linux ile yazılan yeni proje Ekle iletişim kutusunun ekran görüntüsü.](media/newproject-vs2019.png)

   | Proje türü | Description |
   | ------------ | --- |
   | **Yanıp sönme (Raspberry)**           | Bir Raspberry PI cihazı için hedeflenen ve bir LED 'in yanıp sönmesini sağlayan örnek kod içeren proje |
   | **Konsol uygulaması (Linux)** | Bir Linux bilgisayar için hedeflenen ve metni konsola veren örnek kod içeren proje |
   | **Boş proje (Linux)**       | Örnek kod olmadan herhangi bir Linux bilgisayar için hedeflenen proje |
   | **Makefile projesi (Linux)**    | Standart makefile derleme sistemi kullanılarak oluşturulan tüm Linux bilgisayarları için hedeflenen proje |

## <a name="next-steps"></a>Sonraki adımlar

[Linux MSBuild projesi yapılandırma](configure-a-linux-project.md)

::: moniker-end
