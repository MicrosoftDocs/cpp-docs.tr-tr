---
title: Windows, Linux ve macOS 'a vcpkg 'yı yükler
description: Windows, macOS ve Linux 'ta vcpkg 'yı yüklemeyi ve güncelleştirmeyi öğrenin.
ms.date: 12/17/2020
ms.topic: reference
ms.technology: cpp-ide
ms.openlocfilehash: aee9561dc94164c08e4d69ec49f60961392c1854
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684262"
---
# <a name="install-vcpkg-on-windows-linux-and-macos"></a>Windows, Linux ve macOS 'a vcpkg 'yı yükler

Vcpkg GitHub deposundan Yerel bir kopya (kopya) yaparak vcpkg 'yi yüklersiniz.

## <a name="install-vcpkg"></a>Vcpkg 'yi yükler

Özel yönergeler için platformunuzu seçin:

### <a name="linux"></a>[Linux](#tab/linux)

Linux önkoşulları:

- [Git](https://git-scm.com/downloads)
- g + + sürüm 6 veya daha büyük

#### <a name="to-install-linux-development-tools"></a>Linux geliştirme araçları 'nı yüklemek için

Farklı Linux 'ları, farklı paketler yüklemenizi gerektirebilir. Detem, Ubuntu, popOS ve diğer detem tabanlı dağıtımlar üzerinde bu yönergeleri izleyin:

1. Bir kabuk penceresinde, şu komutu çalıştırın:

   **`sudo apt-get update`**

1. Güncelleştirme tamamlandığında, şu komutu çalıştırın:

   **`sudo apt-get install build-essential tar curl zip unzip`**

CentOS hakkında şu yönergeleri izleyin:

1. Bir kabuk penceresinde, şu komutu çalıştırın:

   **`sudo yum install centos-release-scl`**

1. Ardından, aşağıdaki komutları çalıştırarak geliştirme araçlarını yükleyip etkinleştirin:

   **`sudo yum install devtoolset-7`**

   **`scl enable devtoolset-7 bash`**

Diğer dağıtımlar için g + + 6 veya üstünü yüklediğinizden emin olun.

#### <a name="to-copy-and-set-up-vcpkg-on-linux"></a>Linux 'ta vcpkg 'yi kopyalamak ve ayarlamak için

1. Bir kabuk penceresinde, kopyalanmış vcpkg örneğiniz için bir dizin oluşturun. Farklı derleme hedeflerine ait kitaplıkları yüklemeyi planlıyorsanız, hedefi dizin adına eklemek iyi bir fikirdir. *`./x64`* *`./iot`* Diğer bir deyişle, bazı bağlantı noktası derleme sistemleri için yol sorunları yaşıyor olabilirsiniz; bu nedenle, veya gibi boşluklar olmadan kısa yol adları önerilir. Kabuk penceresinde, az önce yaptığınız dizine geçin.

1. GitHub 'dan vcpkg deposunu kopyalayın: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) .

   > **`git clone https://github.com/microsoft/vcpkg`**

   Bu komut, bir alt dizinde bulunan deponun yerel bir kopyasını oluşturur *`vcpkg`* . Bu konum, vcpkg 'nin bu kopyası için vcpkg *kök dizinidir* .

1. Sonra, vcpkg kök dizinine geçin ve vcpkg önyükleyici komutunu çalıştırın:

   > **`./bootstrap-vcpkg.sh`**

   Önyükleyici vcpkg 'yi derleyicinin, araçların ve standart kitaplıkların konumlarıyla birlikte yapılandırır.

### <a name="macos"></a>[macOS](#tab/macos)

MacOS önkoşulları:

- macOS geliştirici araçları
- MacOS 10,14 veya sonrasında şunları da yapmanız gerekir:
  - Homebrew
  - g + + sürüm 6 veya daha büyük

#### <a name="to-install-macos-developer-tools"></a>MacOS geliştirici araçlarını yüklemek için

1. MacOS 10,15 ' de şu komutu terminalde çalıştırın:

   **`xcode-select --install`**

   Ardından, görüntülenen Windows 'daki istemlerle birlikte izleyin.

MacOS 10,14 ve önceki bir deyişle homebrew 'dan g + + yüklemeniz gerekir. Bu yordam yalnızca 10,15 ' dan önce macOS sürümü kullanıyorsanız gereklidir.

#### <a name="to-install-gcc-for-macos-before-1015"></a>MacOS için 10,15 öncesi GCC 'yi yüklemek için

1. Homebrew 'yi yüklemek için Terminal ' i açın ve ardından şu komutu çalıştırın:

   **`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"`**

1. GCC 'nin güncel bir sürümünü yüklemek için şu komutu terminalde çalıştırın:

   **`brew install gcc`**

#### <a name="to-copy-and-set-up-vcpkg-on-macos"></a>MacOS 'ta vcpkg 'yi kopyalamak ve ayarlamak için

1. Terminalde, kopyalanmış vcpkg örneğiniz için bir dizin oluşturun. Farklı derleme hedeflerine ait kitaplıkları yüklemeyi planlıyorsanız, hedefi dizin adına eklemek iyi bir fikirdir. *`./macos`* *`./iot`* Diğer bir deyişle, bazı bağlantı noktası derleme sistemleri için yol sorunları yaşıyor olabilirsiniz; bu nedenle, veya gibi boşluklar olmadan kısa yol adları önerilir. Terminal ' de, az önce yaptığınız dizine geçin.

1. GitHub 'dan vcpkg deposunu kopyalayın: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) .

   > **`git clone https://github.com/microsoft/vcpkg`**

   Bu komut, bir alt dizinde bulunan deponun yerel bir kopyasını oluşturur *`vcpkg`* . Bu konum, vcpkg 'nin bu kopyası için vcpkg *kök dizinidir* .

1. Sonra, vcpkg kök dizinine geçin ve vcpkg önyükleyici komutunu çalıştırın:

   > **`./bootstrap-vcpkg.sh`**

   Önyükleyici vcpkg 'yi derleyicinin, araçların ve standart kitaplıkların konumlarıyla birlikte yapılandırır.

### <a name="windows"></a>[Windows](#tab/windows)

Önkoşullar:

- Windows 7 veya üzeri
- [Windows için Git](https://git-scm.com/downloads)
- [Visual Studio](https://visualstudio.microsoft.com/) 2015 güncelleştirme 3 veya daha fazla İngilizce dil paketi

#### <a name="to-copy-and-set-up-vcpkg-on-windows"></a>Windows 'a vcpkg kopyalamak ve ayarlamak için

1. Bir komut Istemi penceresinde, kopyalanmış vcpkg örneğiniz için bir dizin oluşturun. Farklı derleme hedeflerine ait kitaplıkları yüklemeyi planlıyorsanız, hedefi dizin adına eklemek iyi bir fikirdir. *`C:\src\win32\`* *`C:\dev\iot\`* Diğer bir deyişle, bazı bağlantı noktası derleme sistemleri için yol sorunları yaşıyor olabilirsiniz; bu nedenle, veya gibi boşluklar olmadan kısa yol adları önerilir. Komut penceresinde, az önce yaptığınız dizine geçin.

1. GitHub 'dan vcpkg deposunu kopyalayın: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) .

   > **`git clone https://github.com/microsoft/vcpkg`**

   Bu komut, bir alt dizinde bulunan deponun yerel bir kopyasını oluşturur *`vcpkg`* . Bu konum, vcpkg 'nin bu kopyası için vcpkg *kök dizinidir* .

1. İndirme işlemi tamamlandıktan sonra, *`vcpkg`* komut istemi pencerenizde dizine geçin.

1. Vcpkg kök dizininde vcpkg önyükleyici komutunu çalıştırın:

   > **`bootstrap-vcpkg.bat`**

   Önyükleyici vcpkg 'yi Microsoft C/C++ araçları, kitaplıkları ve Windows SDK konumlarına göre yapılandırır.

---

Vcpkg ayarlandıktan sonra, kitaplıkları yüklemeye hazırsınız demektir. Daha fazla bilgi için bkz. [vcpkg ile kitaplıkları yönetme](manage-libraries-with-vcpkg.md). vcpkg ayrıca Windows üzerinde Visual Studio ile veya herhangi bir platformda Visual Studio Code ile tümleştirilebilir. Daha fazla bilgi için bkz. [vcpkg 'Yi tümleştirme](integrate-vcpkg.md).

## <a name="update-vcpkg"></a>Vcpkg 'yi Güncelleştir

Vcpkg Paket Yöneticisi GitHub 'da düzenli olarak güncelleştirilir. Vcpkg klonınızı en son sürüme güncelleştirmek için vcpkg kök dizininden öğesini çalıştırın **`git pull`** . Bu komut, vcpkg kopyanızı GitHub 'daki sürümle eşitler. İndirme tamamlandıktan sonra, önyükleyiciyi yeniden çalıştırın. Önyükleyici vcpkg programını yeniden oluşturur, ancak yüklü kitaplıklarınızı yerinde bırakır.

## <a name="uninstall-vcpkg"></a>Vcpkg 'yi kaldır

Vcpkg 'yi kaldırmak için dizini silmeniz yeterlidir *`vcpkg`* . Bu dizinin silinmesi vcpkg dağıtımını kaldırır ve vcpkg 'nin yüklü olduğu tüm kitaplıkları kaldırır.

Ancak, yürütülürse **`vcpkg integrate install`** **`vcpkg integrate remove`** , klasör kaldırılmadan önce tümleştirmenin temizlendiğinden emin olmak için yürütmelisiniz. Daha fazla bilgi için bkz. [vcpkg 'Yi tümleştirme](integrate-vcpkg.md).

## <a name="see-also"></a>Ayrıca bkz.

[vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi](./vcpkg.md)\
[GitHub üzerinde vcpkg](https://github.com/Microsoft/vcpkg)\
[Vcpkg 'yi tümleştirin](integrate-vcpkg.md)\
[Vcpkg ile kitaplıkları yönetme](manage-libraries-with-vcpkg.md)\
[vcpkg komut satırı başvurusu](vcpkg-command-line-reference.md)\
[Hızlı başlangıç](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Sık sorulan sorular](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
