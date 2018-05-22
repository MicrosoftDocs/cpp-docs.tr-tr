---
title: Visual Studio'da bir Linux CMake proje yapılandırma | Microsoft Docs
ms.custom: ''
ms.date: 04/28/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: a49d9364b7b39dfddd982519416c9a12b7adf9e6
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/21/2018
---
# <a name="configure-a-linux-cmake-project"></a>Bir Linux CMake proje yapılandırma
  
**Visual Studio 2017 sürüm 15.4** Linux C++ iş yükü yüklediğinizde, Linux CMake desteği varsayılan olarak seçilidir. Şimdi bir Visual Studio projesi dönüştürmek zorunda kalmadan CMake kullanan mevcut kodunuzu temel üzerinde çalışabilir. Kod temeliniz platformlar arası ise, Windows ve Linux gelen Visual Studio içinde hedefleyebilirsiniz. 

Bu konu, Visual Studio'da CMake destek temel olarak bilindiğini olduğunu varsayar. Daha fazla bilgi için bkz: [CMake araçları Visual C++ için](../ide/cmake-tools-for-visual-cpp.md). CMake kendisi hakkında daha fazla bilgi için bkz: [derleme, Test ve paket bilgisayarınızı yazılım ile CMake](https://cmake.org/).

> [!NOTE] 
> Visual Studio'da CMake desteği CMake 3.8 tanıtılan sunucu modu desteği gerektirir. Paket Yöneticisi CMake daha eski bir sürümü sağlıyorsa, çevresinde CMake 3.8 kaynağından oluşturarak çalışabilir.



## <a name="open-a-folder"></a>Bir klasörü açın
Başlamak için tercih **dosya | Açık | Klasör** ana menü veya başka tür gelen `devenv.exe <foldername>` komut satırında. Açtığınız klasör bir CMakeLists.txt dosyasında, kaynak kodu ile birlikte olmalıdır.
Aşağıdaki örnek, bir basit CMakeLists.txt dosya ve .cpp dosyası gösterir:

```cpp
// Hello.cpp

#include <iostream>;
 
int main(int argc, char* argv[])
{
    std::cout << "Hello" << std::endl;
}
```

CMakeLists.txt:

```cmd
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="choose-a-linux-target"></a>Linux bir hedef seçin
Klasör açtıktan hemen Visual Studio CMakeLists.txt dosya ayrıştırır ve x86 hata ayıklama Windows hedefi belirtir. Linux hedeflemek için proje ayarları Linux-Debug veya Linux sürüm olarak değiştirin.

Varsayılan olarak, Visual Studio ilk uzak sistem listede seçer (altında **Araçlar | Seçenekleri | Platformlar arası | Bağlantı Yöneticisi**). Uzak bağlantılar bulunursa, bir oluşturmanız istenir.

Bir Linux hedef belirttikten sonra kaynak Linux makinenize kopyalanır. Ardından, projeniz için CMake önbellek oluşturmak için Linux makinesinde CMake çalıştırın.  

![Linux üzerinde CMake önbellek oluşturmak](media/cmake-linux-1.png "Linux CMake önbellekte oluştur")  

**Visual Studio 2017 15.7 ve sonraki sürümleri:** uzak üstbilgileri için IntelliSense desteği sağlamak için Visual Studio otomatik olarak onları yerel Windows makinenizde bir dizine kopyalar. Daha fazla bilgi için bkz: [uzak üstbilgileri için IntelliSense](configure-a-linux-project.md#remote_intellisense).

## <a name="debug-the-project"></a>Projeyi hata ayıklama  
Uzak sistem üzerindeki kodunuzun hatalarını ayıklamak için CMake hedefleyen bir kesme noktası, select proje ayarın yanındaki araç menüde başlangıç öğesi olarak ayarlayın ve çalıştırın (veya F5 tuşuna basın).

## <a name="configure-cmake-settings-for-linux"></a>Linux CMake ayarlarını yapılandırın
Varsayılan CMake ayarlarını değiştirmek için tercih **CMake | CMake ayarları değiştirme | CMakeLists.txt** ana menüsünden veya sağ CMakeSettings.txt **Çözüm Gezgini** ve **CMake ayarlarını değiştir**. Visual Studio adlı klasörünüzde sonra yeni bir dosya oluşturur `CMakeSettings.json` proje ayarları menü öğesi listelenen varsayılan yapılandırmaları ile doldurulur. Aşağıdaki örnek, önceki kod örneğinde Linux hata ayıklama için varsayılan yapılandırma temel gösterir:

```json
{
      "name": "Linux-Debug",
      "generator": "Unix Makefiles",
      "remoteMachineName": "${defaultRemoteMachineName}",
      "configurationType": "Debug",
      "remoteCMakeListsRoot": "/var/tmp/src/${workspaceHash}/${name}",
      "cmakeExecutable": "/usr/local/bin/cmake",
      "buildRoot": "${env.LOCALAPPDATA}\\CMakeBuilds\\${workspaceHash}\\build\\${name}",
      "remoteBuildRoot": "/var/tmp/build/${workspaceHash}/build/${name}",
      "remoteCopySources": true,
      "remoteCopySourcesOutputVerbosity": "Normal",
      "remoteCopySourcesConcurrentCopies": "10",
      "cmakeCommandArgs": "",
      "buildCommandArgs": "",
      "ctestCommandArgs": "",
      "inheritEnvironments": [ "linux-x64" ]
}
```

`name` Değeri ne olursa olsun, ister olabilir. `remoteMachineName` Değeri birden fazla olması durumunda hedef, hangi uzak bir sisteme belirtir. IntelliSense doğru sistemi seçmenize yardımcı olması Bu alan için etkinleştirilir. Alan `remoteCMakeListsRoot` proje kaynaklarınız için Uzak sistemde kopyalanacağı belirtir. Alan `remoteBuildRoot` yapı çıktı uzak sisteminizde burada oluşturulmuş. Çıktı da yerel olarak tarafından belirtilen konuma kopyalandığını `buildRoot`.

## <a name="building-a-supported-cmake-release-from-source"></a>Kaynak desteklenen CMake sürüm oluşturma
CMake en düşük sürümü, Linux'ta makine 3.8 ve sunucu modunda desteklemelidir gereklidir. Bu bu komutu çalıştırmak doğrulamak için:

```cmd
cmake --version
```

Bu sunucu modu etkin doğrulamak için çalıştırın:

```cmd
cmake -E capabilities
```

Çıktıda "serverMode için" arayın: true. Hatta zaman, kaynak adresinden, açıklandığı gibi derleme yapıldığında yetenekleri denetlemelisiniz unutmayın. Linux sisteminiz sunucu modu etkin önlemek sınırlamaları olabilir.

Almak için yapı Kabuğu'nda kaynağından sistem, Paket Yöneticisi güncel olduğundan ve git ve cmake kullanılabilir olduğundan emin olun, Linux için başlatıldı. İlk olarak, Visual Studio'nun CMake desteği burada kullandığımız CMake kaynaklardan bizim depodaki kopyalama:

```cmd
sudo apt-get update
sudo apt-get install -y git cmake
git clone https://github.com/Microsoft/CMake.git
cd CMake
```

Ardından, aşağıdaki komutları çalıştırın:

```cmd
mkdir out
cd out
cmake ../
make
sudo make install
```

Yukarıdaki komutları, yapı ve /usr/local/bin için CMake geçerli sürümü yükleyin. Sürümü doğrulamak için bu komutu çalıştırmak > = 3.8 ve bu sunucu modu etkinleştirildi:

```cmd
/usr/local/bin/cmake –version
cmake -E capabilities
```

## <a name="see-also"></a>Ayrıca Bkz.
[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)  
[Visual C++ için CMake araçları](../ide/cmake-tools-for-visual-cpp.md)
