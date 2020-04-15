---
title: Visual Studio CMake projelerinde Clang/LLVM desteği
ms.date: 07/01/2019
ms.description: Configure a CMake project in Visual Studio to use the Clang/LLVM toolchain.
helpviewer_keywords:
- Clang support for C++ CMake projects
ms.openlocfilehash: 46bfe788c13df3a37dd9cba654d16cfe4c3fe177
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81323187"
---
# <a name="clangllvm-support-in-visual-studio-cmake-projects"></a>Visual Studio CMake projelerinde Clang/LLVM desteği

::: moniker range="<=vs-2017"

Clang desteği Visual Studio 2019'da mevcuttur.

::: moniker-end

::: moniker range="vs-2019"

Windows veya Linux'u hedefleyen C++ CMake projelerini yeniden oluşturmak ve hata ayıklamak için Clang ile Visual Studio'yı kullanabilirsiniz.

**Windows**: Visual Studio 2019 sürüm 16.1, Windows'u hedefleyen CMake projelerinde Clang/LLVM ile düzenleme, oluşturma ve hata ayıklama desteğini içerir.

**Linux**: Linux CMake projeleri için özel Visual Studio desteği gerekmez. Clang'ı dağıtımınızın paket yöneticisini kullanarak yükleyebilir ve CMakeLists.txt dosyasına uygun komutları ekleyebilirsiniz.

## <a name="install"></a>Yükleme

Visual Studio'da en iyi IDE desteği için, Windows için en son Clang derleyici araçlarını kullanmanızı öneririz. Bunlarzaten yoksa, Visual Studio Installer'ı açarak ve C++ isteğe bağlı **bileşenleriyle Masaüstü geliştirme** altında **Windows için C++ Clang derleyicisini** seçerek bunları yükleyebilirsiniz. Özel bir Clang yüklemesi kullanırken, **v142 yapı araçları bileşeni için C++ Clang-cl'yi kontrol edin.**

![Clang bileşen kurulumu](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Yeni bir yapılandırma oluşturma

CMake projesine yeni bir Clang yapılandırması eklemek için:

1. **Solution Explorer'da** CMakeLists.txt'ye sağ tıklayın ve **proje için CMake ayarlarını**seçin.

1. **Yapılandırmalar** **altında, Yapılandırma Ekle** düğmesine basın:

   ![Yapılandırma ekleme](media/cmake-add-config-icon.png)

1. İstenilen Clang yapılandırmasını seçin (Windows ve Linux için ayrı Clang yapılandırmalarının sağlandığını unutmayın), ardından **Seç**tuşuna basın:

   ![CMake Clang yapılandırması](media/cmake-clang-configuration.png)

1. Bu yapılandırmada değişiklik yapmak için **CMake Ayarlar Düzenleyicisi'ni**kullanın. Daha fazla bilgi için [Visual Studio'daki CMake yapı ayarlarını özelleştir'e](customize-cmake-settings.md)bakın.

## <a name="modify-an-existing-configuration-to-use-clang"></a>Clang'ı kullanmak için varolan yapılandırmayı değiştirme

Clang kullanmak için varolan bir yapılandırmayı değiştirmek için aşağıdaki adımları izleyin:

1. **Solution Explorer'da** CMakeLists.txt'ye sağ tıklayın ve **proje için CMake ayarlarını**seçin.

1. **Genel** altında **Toolset** açılır dosyasını seçin ve istediğiniz Clang araç kümesini seçin:

   ![CMake Clang araç seti](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Özel Clang konumları

Varsayılan olarak, Visual Studio Clang'ı iki yerde arar:

- (Windows) Visual Studio yükleyicisi ile birlikte gelen Clang/LLVM'nin dahili olarak yüklenmiş kopyası.
- (Windows ve Linux) PATH ortamı değişkeni.

**CMake Ayarları'nda cmake**değişkenlerini **CMAKE_C_COMPILER** ve **CMAKE_CXX_COMPILER** ayarlayarak başka bir konum belirtebilirsiniz:

![CMake Clang araç seti](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang uyumluluk modları

Windows yapılandırmaları için CMake varsayılan olarak [Clang-cl](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) modunda Clang'ı çağırır ve Standart Kitaplığın Microsoft uygulamasıyla bağlantı yapar. Varsayılan olarak, **clang-cl.exe** `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`bulunur.

CMake **değişkenleri ve önbellek**altında **CMake Ayarları** bu değerleri değiştirebilirsiniz. **Gelişmiş değişkenleri göster'i**tıklatın. **CMAKE_CXX_COMPILER**bulmak için aşağı kaydırın, ardından farklı bir derleyici yolu belirtmek için **Gözat** düğmesini tıklatın.

## <a name="edit-build-and-debug"></a>Edin, oluşturun ve hata ayıklama

Bir Clang yapılandırması ayarladıktan sonra, projeyi oluşturabilir ve hata ayıklayabilirsiniz. Visual Studio, Clang derleyicisini kullandığınızı algılar ve IntelliSense, vurgulama, gezinme ve diğer düzenleme özellikleri sağlar. Hatalar ve uyarılar **Çıktı Penceresinde**görüntülenir.

Hata ayıklama yaparken, kesme noktaları, bellek ve veri görselleştirme ve diğer çoğu hata ayıklama özelliklerini kullanabilirsiniz. Clang yapılandırmaları için Düzenleme ve Devam gibi derleyiciye bağlı bazı özellikler kullanılamaz.

![CMake Clang hata ayıklama](media/clang-debug-visualize.png)

::: moniker-end
