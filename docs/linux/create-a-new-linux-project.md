---
title: Visual Studio'da yeni bir C++ Linux projesi oluşturun
ms.date: 10/24/2019
description: Visual Studio'da yeni bir MSBuild tabanlı Linux projesi oluşturun.
ms.assetid: 5d7c1d67-bc31-4f96-8622-2b4cf91372fd
ms.openlocfilehash: 1e79dd50756b71aabae7ccec75e57178898e7720
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364347"
---
# <a name="create-a-new-linux-project"></a>Yeni Linux projesi oluşturma

::: moniker range="vs-2015"

Linux projeleri Visual Studio 2017 ve sonrası sürümlerinde mevcuttur.

::: moniker-end

::: moniker range="vs-2017"

İlk olarak, Visual Studio için **Linux Geliştirme İş Yükünü** yüklü olduğundan emin olun. Daha fazla bilgi için Linux [iş yükünü İndir, yükle ve kurulum una](download-install-and-setup-the-linux-development-workload.md)bakın.

Çapraz platform derlemesi için CMake'i kullanmanızı öneririz. CMake desteği Visual Studio 2019'da daha eksiksizdir. CMake bir seçenek değilse ve Linux için derlemek için genişletmek istediğiniz varolan bir Windows Visual Studio çözümüne sahipseniz, **Paylaşılan Öğeler** projesiyle birlikte Windows çözümüne bir Visual Studio Linux projesi ekleyebilirsiniz. Paylaşılan Öğeler projesinde her iki platform arasında paylaşılan kodu koyun ve Windows ve Linux projelerinden bu projeye bir başvuru ekleyin.

## <a name="to-create-a-new-linux-project"></a>Yeni bir Linux projesi oluşturmak için

Visual Studio 2017'de yeni bir Linux projesi oluşturmak için aşağıdaki adımları izleyin:

1. Visual **Studio'da Dosya > Yeni Proje'yi** seçin veya **Ctrl + Shift + N**tuşuna basın.
1. Visual **C++ > Linux** düğümü > Çapraz Platform'u seçin ve ardından oluşturmak için proje türünü seçin. Bir **Ad** ve **Konum**girin ve **Tamam'ı**seçin.

   ![Yeni Linux Projesi](media/newproject.png)

   | Proje Türü | Açıklama |
   | ------------ | --- |
   | **Blink (Ahududu)**           | Bir LED'i yanıp sönen örnek kodlu raspberry Pi cihazı için hedeflenen proje |
   | **Konsol Uygulaması (Linux)** | Konsola metin çıkışı örnek kodu ile herhangi bir Linux bilgisayarı için hedeflenen proje |
   | **Boş Proje (Linux)**       | Örnek kodu olmayan herhangi bir Linux bilgisayarı için hedeflenen proje |
   | **Makefile Projesi (Linux)**    | Proje herhangi bir Linux bilgisayar için hedeflenen, standart bir Makefile inşa sistemi kullanılarak inşa |

## <a name="next-steps"></a>Sonraki adımlar

[Linux projesi yapılandırma](configure-a-linux-project.md)

::: moniker-end

::: moniker range="vs-2019"

İlk olarak, Visual Studio için **Linux Geliştirme İş Yükünü** yüklü olduğundan emin olun. Daha fazla bilgi için [Bkz. Linux iş yükünü İndir, yükle ve ayarla.](download-install-and-setup-the-linux-development-workload.md)

Visual Studio'da Linux için yeni bir C++ projesi oluşturduğunuzda, visual studio projesi veya CMake projesi oluşturmayı seçebilirsiniz. Bu makalede, Visual Studio projesinin nasıl oluşturulacak olduğu açıklanmaktadır. Genel olarak, açık kaynak kod içerebilecek veya platformlar arası geliştirme için derlemek istediğiniz yeni projeler için Visual Studio ile CMake'i kullanmanızı öneririz. Bir CMake projesi ile hem Windows'da hem de Linux'ta aynı projeyi oluşturabilir ve hata ayıklayabilirsiniz. Daha fazla bilgi için [bkz.](cmake-linux-project.md)

Linux için derlemek için genişletmek istediğiniz varolan bir Windows Visual Studio çözümünüz varsa ve CMake bir seçenek değilse, **Paylaşılan Öğeler** projesiyle birlikte Windows çözümüne bir Visual Studio Linux projesi ekleyebilirsiniz. Paylaşılan Öğeler projesinde her iki platform arasında paylaşılan kodu koyun ve Windows ve Linux projelerinden bu projeye bir başvuru ekleyin.

## <a name="to-create-a-new-linux-project"></a>Yeni bir Linux projesi oluşturmak için

Visual Studio 2019'da yeni bir Linux projesi oluşturmak için aşağıdaki adımları izleyin:

1. Visual **Studio'da Dosya > Yeni Proje'yi** seçin veya **Ctrl + Shift + N**tuşuna basın.
1. **Dili** **C++** olarak ayarlayın ve "Linux" aramasını yapın. Oluşturmak için proje türünü seçin ve sonra **İleri'yi**seçin. **Ad** ve **Konum**girin ve **Oluştur'u**seçin.

   ![Yeni Linux Projesi](media/newproject-vs2019.png)

   | Proje Türü | Açıklama |
   | ------------ | --- |
   | **Blink (Ahududu)**           | Bir LED'i yanıp sönen örnek kodlu raspberry Pi cihazı için hedeflenen proje |
   | **Konsol Uygulaması (Linux)** | Konsola metin çıkışı örnek kodu ile herhangi bir Linux bilgisayarı için hedeflenen proje |
   | **Boş Proje (Linux)**       | Örnek kodu olmayan herhangi bir Linux bilgisayarı için hedeflenen proje |
   | **Makefile Projesi (Linux)**    | Proje herhangi bir Linux bilgisayar için hedeflenen, standart bir Makefile inşa sistemi kullanılarak inşa |

## <a name="next-steps"></a>Sonraki adımlar

[Linux projesi yapılandırma](configure-a-linux-project.md)

::: moniker-end
