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

Clang desteği Visual Studio 2019 ' de kullanılabilir.

::: moniker-end

::: moniker range="vs-2019"

Windows veya Linux 'u hedefleyen C++ CMake projelerini düzenlemek ve hatalarını ayıklamak için Visual Studio ile Clang kullanabilirsiniz.

**Windows**: Visual Studio 2019 sürüm 16,1, Windows 'U hedefleyen CMake projelerinde Clang/LLVM ile ekleme, oluşturma ve hata ayıklama desteği içerir.

**Linux**: Linux CMake projeleri Için özel Visual Studio desteği gerekli değildir. Clang 'yi, kendi paket yöneticisini kullanarak yükleyebilir ve CMakeLists. txt dosyasına uygun komutları ekleyebilirsiniz.

## <a name="install"></a>Yükleme

Visual Studio 'da en iyi IDE desteği için, Windows için en son Clang derleyicisi araçlarını kullanmanızı öneririz. Henüz yoksa, Visual Studio Yükleyicisi açarak ve C++ isteğe bağlı bileşenleriyle **masaüstü geliştirme** bölümünde **Windows Için c++ Clang derleyicisi** ' nı seçerek yükleyebilirsiniz. Özel bir Clang yüklemesi kullanırken, **v142 derleme araçları bileşeni için C++ Clang-CL** ' yi kontrol edin.

![Clang bileşeni yüklemesi](media/clang-install-vs2019.png)

## <a name="create-a-new-configuration"></a>Yeni bir yapılandırma oluştur

CMake projesine yeni bir Clang yapılandırması eklemek için:

1. **Çözüm Gezgini** Içinde CMakeLists. txt dosyasına sağ tıklayın ve **CMake ayarlarını proje için**seçin.

1. **Yapılandırmalar**' ın altında, **yapılandırma Ekle** düğmesine basın:

   ![Yapılandırma ekleme](media/cmake-add-config-icon.png)

1. İstenen Clang yapılandırmasını seçin (Windows ve Linux için ayrı Clang yapılandırmalarının sağlandığını unutmayın) ve ardından **Seç**' e basın:

   ![CMake Clang yapılandırması](media/cmake-clang-configuration.png)

1. Bu yapılandırmada değişiklik yapmak için **CMake ayarları düzenleyicisini**kullanın. Daha fazla bilgi için bkz. [Visual Studio 'Da CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md).

## <a name="modify-an-existing-configuration-to-use-clang"></a>Varolan bir yapılandırmayı Clang kullanacak şekilde değiştirme

Varolan bir yapılandırmayı Clang kullanacak şekilde değiştirmek için şu adımları izleyin:

1. **Çözüm Gezgini** Içinde CMakeLists. txt dosyasına sağ tıklayın ve **CMake ayarlarını proje için**seçin.

1. **Genel** altında **araç kümesi** açılan listesini seçin ve istenen Clang araç takımını seçin:

   ![CMake Clang araç takımı](media/cmake-clang-toolset.png)

## <a name="custom-clang-locations"></a>Özel Clang konumları

Varsayılan olarak, Visual Studio iki yerde Clang 'yi arar:

- Pencerelerin Visual Studio yükleyicisi ile birlikte gelen, dahili olarak yüklenen Clang/LLVM kopyası.
- (Windows ve Linux) PATH ortam değişkeni.

**CMake ayarlarında** **CMAKE_C_COMPILER** ve **CMAKE_CXX_COMPILER** CMake değişkenlerini ayarlayarak başka bir konum belirtebilirsiniz:

![CMake Clang araç takımı](media/clang-location-cmake.png)

## <a name="clang-compatibility-modes"></a>Clang uyumluluk modları

Windows yapılandırmalarında CMake, [Clang-CL](https://llvm.org/devmtg/2014-04/PDFs/Talks/clang-cl.pdf) modunda Clang 'Yi ve standart kitaplığın Microsoft uygulamasıyla bağlantıları çağırır. Varsayılan olarak, **Clang-CL. exe** ' de `C:\Program Files (x86)\Microsoft Visual Studio\2019\Common7\IDE\CommonExtensions\Microsoft\Llvm\bin`bulunur.

CMake **değişkenleri ve önbelleği**altındaki **CMake ayarlarında** bu değerleri değiştirebilirsiniz. **Gelişmiş değişkenleri göster**' e tıklayın. **CMAKE_CXX_COMPILER**bulmak için aşağı kaydırın ve ardından farklı bir derleyici yolu belirtmek Için, **Gözden** geçirme düğmesine tıklayın.

## <a name="edit-build-and-debug"></a>Düzenle, oluştur ve hata ayıkla

Bir Clang yapılandırması ayarladıktan sonra, projeyi derleyip hata ayıklaması yapabilirsiniz. Visual Studio, Clang derleyicisini kullandığınızı algılar ve IntelliSense, vurgulama, gezinme ve diğer düzen özelliklerini sağlar. Hatalar ve uyarılar **Çıkış penceresi**görüntülenir.

Hata ayıklama sırasında kesme noktaları, bellek ve veri görselleştirme ve diğer birçok hata ayıklama özelliği kullanabilirsiniz. Düzenle ve devam et gibi bazı derleyiciye bağımlı özellikler Clang yapılandırmalarında kullanılamaz.

![CMake Clang hata ayıklaması](media/clang-debug-visualize.png)

::: moniker-end
