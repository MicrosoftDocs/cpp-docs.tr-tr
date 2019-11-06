---
title: Visual Studio 'da C++ yeni bir Linux projesi oluşturma
ms.date: 10/24/2019
description: Visual Studio 'da yeni bir MSBuild tabanlı Linux projesi oluşturun.
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 5d5fa67566d86edb2ed0389fdbe38866b47e2211
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73626739"
---
# <a name="create-a-new-linux-project"></a>Yeni Linux projesi oluşturma

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

   ![Yeni Linux projesi](media/newproject.png)

   | Proje türü | Açıklama |
   | ------------ | --- |
   | **Yanıp sönme (Raspberry)**           | Bir Raspberry PI cihazı için hedeflenen ve bir LED 'in yanıp sönmesini sağlayan örnek kod içeren proje |
   | **Konsol uygulaması (Linux)** | Bir Linux bilgisayar için hedeflenen ve metni konsola veren örnek kod içeren proje |
   | **Boş proje (Linux)**       | Örnek kod olmadan herhangi bir Linux bilgisayar için hedeflenen proje |
   | **Makefile projesi (Linux)**    | Standart makefile derleme sistemi kullanılarak oluşturulan tüm Linux bilgisayarları için hedeflenen proje |

## <a name="next-steps"></a>Sonraki adımlar

[Linux projesi yapılandırma](configure-a-linux-project.md)

::: moniker-end

::: moniker range="vs-2019"

İlk olarak, Visual Studio için **Linux geliştirme Iş yükünüzün** yüklü olduğundan emin olun. Daha fazla bilgi için bkz. [Linux iş yükünü indirme, yükleme ve ayarlama](download-install-and-setup-the-linux-development-workload.md).

Visual Studio 'da Linux için C++ yeni bir proje oluşturduğunuzda, bir Visual Studio projesi veya CMake projesi oluşturmayı seçebilirsiniz. Bu makalede, Visual Studio projesinin nasıl oluşturulacağı açıklanır. Genel olarak, açık kaynak kodu içerebilen veya platformlar arası geliştirme için derlemeyi planladığınız yeni projeler için CMake 'i Visual Studio ile kullanmanızı öneririz. CMake projesi ile hem Windows hem de Linux 'ta aynı projeyi oluşturabilir ve hata ayıklayabilirsiniz. Daha fazla bilgi için bkz. [Linux CMake projesi oluşturma ve yapılandırma](cmake-linux-project.md).

Linux için derlemek üzere genişletmek istediğiniz mevcut bir Windows Visual Studio çözümünüz varsa ve CMake bir seçenek değilse, Windows çözümüne, **Paylaşılan öğeler** projesiyle birlikte bir Visual Studio Linux projesi ekleyebilirsiniz. Paylaşılan öğeler projesindeki her iki platform arasında paylaşılan kodu koyun ve Windows ve Linux projelerinden bu projeye bir başvuru ekleyin.

## <a name="to-create-a-new-linux-project"></a>Yeni bir Linux projesi oluşturmak için

Visual Studio 2019 ' de yeni bir Linux projesi oluşturmak için aşağıdaki adımları izleyin:

1. Visual Studio 'da **dosya > yeni proje** ' yi seçin veya **CTRL + SHIFT + N**tuşlarına basın.
1. **Dili** olarak **C++** ayarlayın ve "Linux" araması yapın. Oluşturulacak proje türünü seçin ve ardından **İleri**' yi seçin. Bir **ad** ve **konum**girin ve **Oluştur**' u seçin.

   ![Yeni Linux projesi](media/newproject-vs2019.png)

   | Proje türü | Açıklama |
   | ------------ | --- |
   | **Yanıp sönme (Raspberry)**           | Bir Raspberry PI cihazı için hedeflenen ve bir LED 'in yanıp sönmesini sağlayan örnek kod içeren proje |
   | **Konsol uygulaması (Linux)** | Bir Linux bilgisayar için hedeflenen ve metni konsola veren örnek kod içeren proje |
   | **Boş proje (Linux)**       | Örnek kod olmadan herhangi bir Linux bilgisayar için hedeflenen proje |
   | **Makefile projesi (Linux)**    | Standart makefile derleme sistemi kullanılarak oluşturulan tüm Linux bilgisayarları için hedeflenen proje |

## <a name="next-steps"></a>Sonraki adımlar

[Linux projesi yapılandırma](configure-a-linux-project.md)

::: moniker-end
