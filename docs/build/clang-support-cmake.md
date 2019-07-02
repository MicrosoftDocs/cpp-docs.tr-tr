---
title: Visual Studio CMake projelerini clang/LLVM desteği
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++
ms.openlocfilehash: 6773d9cdb076ef305ba635306f3bc9c6575d2203
ms.sourcegitcommit: b233f05adae607f75815111006a771c432df5a9d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67518168"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Visual Studio CMake projelerini clang/LLVM desteği

::: moniker range="<=vs-2017"

Clang desteği, Visual Studio 2019 içinde kullanılabilir.

::: moniker-end

::: moniker range="vs-2019"

Visual Studio ile Clang düzenleme ve hata ayıklama için kullanabileceğiniz C++ , hedef Windows veya Linux CMake projeleri.

**Windows**: Visual Studio 2019 sürüm 16.1 düzenleme, derleme ve Clang/LLVM ile Windows hedefleyen CMake projelerinde hata ayıklama desteği içerir. 

**Linux**: Linux CMake projeleri için özel Visual Studio desteği gereklidir. Clang, distro ait Paket Yöneticisi'ni kullanarak yükleyebilir ve uygun komutları CMakeLists.txt dosyasına ekleyin.

## <a name="install"></a>Yükleme

Visual Studio'da en iyi IDE desteği için Windows için en son Clang derleyici araçlarını kullanmanızı öneririz. Bu zaten yoksa, bunları Visual Studio Yükleyicisi'ni açarak ve yükleyebileceğiniz **Clang derleyici Windows için** altında **ile masaüstü geliştirme C++**  isteğe bağlı bileşenler.

![Clang bileşeni yükleme](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Yeni yapılandırma oluşturma

Yeni bir Clang yapılandırması için bir CMake projesini eklemek için:

1. Bir cmakelists.txt dosyası sağ **Çözüm Gezgini** ve **CMake proje ayarlarını**.

1. Altında **yapılandırmaları**, basın **Yapılandırması Ekle** düğmesi:

   ![Yapılandırma Ekle](media/cmake-add-config-icon.png)

1. İstenen Clang yapılandırma (Not), Windows ve Linux için ayrı Clang yapılandırmaları sağlanan tuşuna seçin **seçin**:

   ![CMake, Clang yapılandırma](media/cmake-clang-configuration.png)

1. Bu yapılandırma değişiklikleri yapmak için **CMake ayarları Düzenleyicisi**. Daha fazla bilgi için [özelleştirme CMake derleme ayarları Visual Studio'da](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang kullanmak için var olan bir yapılandırmasını Değiştir

Clang kullanmak için mevcut bir yapılandırmayı değiştirmek için aşağıdaki adımları izleyin:

1. Bir cmakelists.txt dosyası sağ **Çözüm Gezgini** ve **CMake proje ayarlarını**.

1. Altında **genel** seçin **araç takımı** açılır ve istenen Clang araç takımı seçin:

   ![CMake, Clang araç takımı](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Özel Clang konumlar

Varsayılan olarak, Visual Studio iki yerde Clang arar:

- (Windows) Visual Studio Yükleyicisi ile birlikte gelen Clang/LLVM yüklü dahili olarak kopyalanması.
- (Windows ve Linux) PATH ortam değişkenine.

Başka bir konuma ayarlayarak belirtebilirsiniz **CMAKE_C_COMPILER** ve **CMAKE_CXX_COMPILER** CMake değişkenleri **CMake ayarlarını**:

![CMake, Clang araç takımı](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang uyumluluk modu

Windows yapılandırmaları için varsayılan olarak CMake, Clang çağırır [clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) modu ve standart Kitaplığı'nın Microsoft uygulaması bağlantıları. Varsayılan olarak, **clang cl.exe** bulunan `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`.

 Bu değerleri değiştirebilirsiniz **CMake ayarlarını** altında **CMake değişkenleri ve önbellek**. Tıklayın **değişkenleri Gelişmiş Göster**. Bul aşağı kaydırın **CMAKE_CXX_COMPILER**, ardından **Gözat** düğmesini farklı derleyici yolu belirtin.

## <a name="edit-build-and-debug"></a>Düzenleme, derleme ve hata ayıklama

Bir Clang yapılandırması ayarlandıktan sonra yapı ve proje hata ayıklama. Visual Studio, Clang derleyici kullanıyor ve IntelliSense, gezinti ve diğer düzenleme özellikleri vurgulama sağlar algılar. Hatalar ve uyarılar görüntülenir **çıkış penceresine**.

Hata ayıklarken kesme noktaları, bellek ve veri Görselleştirme ve diğer hata ayıklama özelliklerinin çoğu kullanabilirsiniz. Düzenle ve devam et gibi bazı derleyici bağımlı özellikleri Clang yapılandırmalar için kullanılabilir değildir.

![CMake Clang hata ayıklama](media/clang-debug-visualize.png)

::: moniker-end
