---
title: Visual Studio 'da CMake Linux projesi oluşturma
description: Visual Studio 'da Linux CMake projesi oluşturma
ms.date: 08/06/2020
ms.assetid: f8707b32-f90d-494d-ae0b-1d44425fdc25
ms.openlocfilehash: 1b622bcd2af49ee51f7546be4c7a6d804c3102d0
ms.sourcegitcommit: 2034f8e744a8b36cff8b15e9a5cfe684afebadfb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2020
ms.locfileid: "88043830"
---
# <a name="create-a-cmake-linux-project-in-visual-studio"></a>Visual Studio 'da CMake Linux projesi oluşturma

::: moniker range="vs-2015"
Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir. Bu sürümlerin belgelerini görmek için, içindekiler tablosunun üstünde bulunan **Sürüm** açılan listesini **Visual Studio 2017** veya **Visual Studio 2019**olarak ayarlayın.
::: moniker-end

::: moniker range=">=vs-2017"

Platformlar arası olan veya açık kaynak oluşturacak projeler için CMake kullanmanızı öneririz. CMake projelerini Windows, Linux için Windows alt sistemi (WSL) ve uzak sistemler üzerinde aynı kaynak kodu oluşturmak ve hata ayıklamak için kullanabilirsiniz.

## <a name="before-you-begin"></a>Başlamadan önce

İlk olarak, CMake bileşeni dahil olmak üzere Visual Studio Linux iş yükünün yüklü olduğundan emin olun. Bu, Visual Studio yükleyicisindeki C++ iş yüküyle **Linux geliştirme aşamasındadır** . Yüklü olduğundan emin değilseniz bkz. [Visual Studio 'Da C++ Linux iş yükünü yükleme](download-install-and-setup-the-linux-development-workload.md) .

Ayrıca, aşağıdakilerin uzak makinede yüklü olduğundan emin olun:

- GCC
- GDB
- rsync
- zip
- dokja-derleme (Visual Studio 2019 veya üzeri)
::: moniker-end

::: moniker range="vs-2017"
Visual Studio 'da CMake desteği, CMake 3,8 ' de sunulan sunucu modu desteğini gerektirir. Microsoft tarafından sağlanmış bir CMake değişkeni için, en son önceden oluşturulmuş ikilileri adresinden indirin [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) .

İkililer ' de yüklenir `~/.vs/cmake` . İkili dosyaları dağıttıktan sonra projeniz otomatik olarak yeniden oluşturur. ÜzerindeCMakeSettings.jsalan tarafından belirtilen CMake `cmakeExecutable` geçersiz ( *CMakeSettings.json* yok veya desteklenmeyen bir sürümdür) ve önceden oluşturulmuş ikili dosyalar varsa, Visual Studio `cmakeExecutable` önceden oluşturulmuş ikilileri yoksayar ve kullanır.

Visual Studio 2017, sıfırdan CMake projesi oluşturamaz, ancak sonraki bölümde açıklandığı gibi var olan bir CMake projesini içeren bir klasörü açabilirsiniz.
::: moniker-end

::: moniker range=">=vs-2019"
Visual Studio 2019 ' i, uzak bir Linux sisteminde veya WSL 'de derlemek ve hata ayıklamak için kullanabilir ve CMake bu sistemde çağrılacaktır. CMake sürüm 3,14 veya üzeri hedef makinede yüklü olmalıdır.

Hedef makinede CMake 'in son sürümüne sahip olduğundan emin olun. Genellikle, bir dağıtımın varsayılan paket yöneticisi tarafından sunulan sürüm, Visual Studio için gereken tüm özellikleri desteklemeye yetecek kadar güncel değildir. Visual Studio 2019, Linux sisteminde bir CMake son sürümünün yüklü olup olmadığını algılar. Hiçbiri bulunmazsa, Visual Studio, düzenleyici bölmesinin üst kısmında bir bilgi çubuğu gösterir. Sizin için CMake 'i yüklemenizi sağlar [https://github.com/Microsoft/CMake/releases](https://github.com/Microsoft/CMake/releases) .

Visual Studio 2019 ile sıfırdan CMake projesi oluşturabilir veya var olan bir CMake projesini açabilirsiniz. Yeni bir CMake projesi oluşturmak için aşağıdaki yönergeleri izleyin. Ya da bir CMake projeniz zaten varsa bir [CMake proje klasörü açmaya](#open-a-cmake-project-folder) devam edin.

## <a name="create-a-new-linux-cmake-project"></a>Yeni bir Linux CMake projesi oluştur

Visual Studio 2019 'de yeni bir Linux CMake projesi oluşturmak için:

1. Visual Studio 'da **dosya > yeni proje** ' yi seçin veya **CTRL + SHIFT + N**tuşlarına basın.
1. **Dili** **C++** olarak ayarlayın ve "CMake" araması yapın. Ardından **İleri**' yi seçin. Bir **ad** ve **konum**girin ve **Oluştur**' u seçin.

Alternatif olarak, Visual Studio 2019 ' de kendi CMake projenizi açabilirsiniz. Aşağıdaki bölümde açıklanmaktadır.

Visual Studio yalnızca yürütülebilir dosya adı ve gereken en düşük CMake sürümü ile en az bir *CMakeLists.txt* dosyası oluşturur. Bu dosyayı dilediğiniz gibi el ile düzenleyebilirsiniz; Visual Studio, değişikliklerinizin üzerine hiçbir değişiklik yazmaz.

Visual Studio 2019 ' de CMake betiklerinizi anlayabilmeniz, düzenlemeniz ve yazmak için aşağıdaki kaynaklara bakın:

- [Visual Studio 'da CMake için düzenleyici belge](https://devblogs.microsoft.com/cppblog/in-editor-documentation-for-cmake-in-visual-studio/)
- [CMake betikleri için kod gezintisi](https://devblogs.microsoft.com/cppblog/code-navigation-for-cmake-scripts/)
- [CMake projelerinde dosyaları ve hedefleri kolayca ekleyin, kaldırın ve yeniden adlandırın](https://devblogs.microsoft.com/cppblog/easily-add-remove-and-rename-files-and-targets-in-cmake-projects/)
::: moniker-end

::: moniker range=">=vs-2017"
## <a name="open-a-cmake-project-folder"></a>CMake proje klasörü aç

Var olan bir CMake projesi içeren bir klasörü açtığınızda, Visual Studio IntelliSense ve yapıları otomatik olarak yapılandırmak için CMake önbelleğindeki değişkenleri kullanır. Yerel yapılandırma ve hata ayıklama ayarları JSON dosyalarında depolanır. İsteğe bağlı olarak, bu dosyaları Visual Studio kullanan diğer kullanıcılarla paylaşabilirsiniz.

Visual Studio *CMakeLists.txt* dosyalarını değiştirmez. Bu, aynı proje üzerinde çalışan başkalarının mevcut araçlarını kullanmaya devam etmesine olanak tanır. *CMakeLists.txt*düzenlemeleri kaydettiğinizde veya bazı durumlarda *CMakeSettings.js*için, Visual Studio önbelleği yeniden üretin. **Mevcut bir önbellek** yapılandırması kullanıyorsanız, Visual Studio önbelleği değiştirmez.

Visual Studio 'da CMake desteği hakkında genel bilgi için bkz. [Visual Studio 'Da CMake projeleri](../build/cmake-projects-in-visual-studio.md). Devam etmeden önce bunu okuyun.

Başlamak için, ana menüden **Dosya**  >  **Aç**  >  **klasörünü** seçin veya `devenv.exe <foldername>` bir [Geliştirici komut istemi](../build/building-on-the-command-line.md) penceresinde yazın. Açtığınız klasörde, kaynak kodunuzla birlikte bu dosyada bir *CMakeLists.txt* dosyası olmalıdır.

Aşağıdaki örnekte basit bir *CMakeLists.txt* dosyası ve. cpp dosyası gösterilmektedir:

```cpp
// hello.cpp

#include <iostream>

int main(int argc, char* argv[])
{
    std::cout << "Hello from Linux CMake" << std::endl;
}
```

*CMakeLists.txt*:

```txt
cmake_minimum_required(VERSION 3.8)
project (hello-cmake)
add_executable(hello-cmake hello.cpp)
```

## <a name="next-steps"></a>Sonraki adımlar

[Linux CMake projesi yapılandırma](cmake-linux-configure.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da CMake projeleri](../build/cmake-projects-in-visual-studio.md)<br/>
::: moniker-end
