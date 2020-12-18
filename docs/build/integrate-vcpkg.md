---
title: Vcpkg 'yi Visual Studio veya Visual Studio Code tümleştirme
description: Vcpkg 'yı Windows üzerinde Visual Studio veya macOS ve Linux 'ta Visual Studio Code tümleştirme hakkında bilgi edinin.
ms.date: 12/11/2020
ms.technology: cpp-ide
ms.openlocfilehash: b6f092313dde14b10a05d4cff0904adf5174b264
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684267"
---
# <a name="integrate-vcpkg-with-visual-studio-or-visual-studio-code"></a>Vcpkg 'yi Visual Studio veya Visual Studio Code tümleştirme

vcpkg, C ve C++ kitaplıkları için platformlar arası bir komut satırı paket yöneticisidir. Bunu Windows üzerinde Visual Studio veya Linux ve macOS üzerinde Visual Studio Code tümleştirebilirsiniz.

## <a name="integrate-with-visual-studio-on-windows"></a>Windows üzerinde Visual Studio ile tümleştirme

### <a name="integrate-per-user"></a>Kullanıcı başına tümleştirme

Vcpkg kök dizininden, **`vcpkg integrate install`** Visual Studio 'yu, tüm vcpkg üst bilgi dosyalarını ve ikili dosyaları Kullanıcı başına temelinde bulacak şekilde yapılandırmak için komutunu çalıştırın. Visual Studio 'da VC + + dizin yollarını düzenlemeniz gerekmez. Vcpkg 'nin birden çok klonunuz varsa, bu komutu çalıştırdığınız kopya yeni varsayılan konum olur.

Artık klasörü veya başlık adını yazarak üst bilgileri dahil edebilirsiniz ve otomatik tamamlama size yardımcı olur. Kitaplıklara bağlamak veya proje başvuruları eklemek için herhangi bir ek adım gerekmez. Aşağıdaki çizimde, Visual Studio 'Nun üstbilgileri nasıl bulduğu gösterilmektedir *`azure-storage-cpp`* . vcpkg, üst bilgilerini *`/installed`* hedef platforma göre bölümlenmiş alt klasöre koyar. Aşağıdaki diyagramda, *`/was`* kitaplık için alt klasördeki içerme dosyalarının listesi gösterilmektedir:

![Visual Studio düzenleyicisinde bir IntelliSense otomatik tamamlama açılır penceresi](media/vcpkg-intellisense.png "vcpkg ve IntelliSense")

### <a name="integrate-per-project"></a>Proje başına tümleştirme

Bir kitaplığın, etkin vcpkg örneğindeki sürümden farklı olan belirli bir sürümünü kullanmanız gerekiyorsa, şu adımları izleyin:

1. Vcpkg 'nin yeni bir kopyasını oluşturun. Daha fazla bilgi için bkz. [vcpkg 'Yı Install](install-vcpkg.md).

1. Yeni vcpkg kök dizinine geçin.

1. Kitaplığın portfile dosyasını, ihtiyacınız olan sürümü alacak şekilde değiştirin.

1. Öğesini çalıştırın **`vcpkg install <library>`** . Daha fazla bilgi için bkz. [vcpkg ile kitaplıkları yönetme](manage-libraries-with-vcpkg.md).

1. **`vcpkg integrate project`** Projeye göre bu kitaplığa başvuran bir NuGet paketi oluşturmak için kullanın.

## <a name="integrate-with-visual-studio-code-on-linux-or-macos"></a>Linux veya macOS üzerinde Visual Studio Code tümleştirme

Kabuğunuzun veya Terminal pencerenizde Dizin ' i vcpkg kök dizinine değiştirin. Ardından **`./vcpkg integrate install`** Linux veya macOS üzerinde Visual Studio Code yapılandırmak için öğesini çalıştırın. Bu komut, vcpkg araçlarının ve kitaplıklarının konumunu ayarlar ve kaynak dosyalarında IntelliSense 'i etkinleştirilir.

## <a name="remove-vcpkg-integration"></a>Vcpkg tümleştirmesini kaldır

**`integrate`** Seçeneğini kullandıysanız, vcpkg örneğini kaldırmadan önce tümleştirmeyi kaldırmanız gerekir. Tümleştirmeyi kaldırmak ve gidermek için dizinleri vcpkg kök dizinine değiştirin. Windows 'da, **`vcpkg integrate remove`** tümleştirmenin temizlendiğinden emin olmak için çalıştırın. Linux veya macOS üzerinde **`./vcpkg integrate remove`** komutunu çalıştırın.

## <a name="see-also"></a>Ayrıca bkz.

[vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi](./vcpkg.md)\
[GitHub üzerinde vcpkg](https://github.com/Microsoft/vcpkg)\
[Vcpkg 'yi yükler](install-vcpkg.md)\
[Vcpkg ile kitaplıkları yönetme](manage-libraries-with-vcpkg.md)\
[vcpkg komut satırı başvurusu](vcpkg-command-line-reference.md)\
[Hızlı başlangıç](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Sık sorulan sorular](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
