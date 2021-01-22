---
title: 'Öğretici: uzak bir Windows makinesindeki CMake projesinde hata ayıklama'
ms.date: 12/4/2020
ms.topic: tutorial
description: CMake projesi oluşturmak ve derlemek için Windows üzerinde Visual Studio C++ kullanma. Bu durumda, uzak bir Windows makinesinde dağıtıp hata ayıklaması yapılır.
ms.openlocfilehash: 742ee831fc30ffe291d68ff97ad4238e57c7e21d
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98668920"
---
# <a name="tutorial-debug-a-cmake-project-on-a-remote-windows-machine"></a>Öğretici: uzak bir Windows makinesindeki CMake projesinde hata ayıklama

Bu öğretici, uzak bir Windows makinesinde dağıtabileceğiniz ve hata ayıklayacağınız bir CMake projesi oluşturmak ve derlemek için Windows üzerinde Visual Studio C++ kullanır. Bu öğretici Windows ARM64 'e özeldir, ancak adımlar diğer mimarilerde genelleştirilemez.

Visual Studio 'da, ARM64 için varsayılan hata ayıklama deneyimi bir ARM64 Windows makinesinde uzaktan hata ayıklaması yapılır. Bu öğreticide gösterildiği gibi, hata ayıklama ayarlarınızı yapılandırmadan bir ARM64 CMake projesinde hata ayıklamaya çalışırsanız, Visual Studio 'Nun uzak makineyi bulamamasına ilişkin bir hata alırsınız.

Bu öğreticide aşağıdakilerin nasıl yapılacağını öğreneceksiniz:

> [!div class="checklist"]
>
> * CMake projesi oluşturma
> * ARM64 için derlemek üzere bir CMake projesi yapılandırma
> * CMake projesini uzak ARM64 Windows makinesinde çalışacak şekilde yapılandırma
> * uzak ARM64 Windows makinesinde çalışan bir CMake projesinde hata ayıklama

## <a name="prerequisites"></a>Önkoşullar

### <a name="on-the-host-machine"></a>Konak makinede

Platformlar arası C++ geliştirmesi için Visual Studio 'yu ayarlamak için, hedef mimari için derleme araçlarını kurun. Bu öğreticide, aşağıdakileri yaparak ARM64 derleme araçlarını yüklemelisiniz:

1. Visual Studio Yükleyicisi çalıştırın. Visual Studio 'Yu henüz yüklemediyseniz bkz. [Visual Studio 'Yu yükleme](https://docs.microsoft.com/visualstudio/install/install-visual-studio#:~:text=Install%20Visual%20Studio%201%20Make%20sure%20your%20computer,...%204%20Choose%20workloads.%20...%20More%20items...%20)
1. Visual Studio Yükleyicisi giriş ekranında **Değiştir**' i seçin.
1. Üstteki seçeneklerden **bağımsız bileşenler**' i seçin.
1. **Derleyiciler, derleme araçları ve çalışma zamanları** bölümüne gidin.
1. Aşağıdakilerin seçili olduğundan emin olun:
    - **Windows için C++ CMake araçları**
    - **MSVC v142-VS 2019 C++ ARM64 derleme araçları (en son)** Derleme araçlarını değil, derleme araçlarını seçmeniz `ARM64` `ARM` (64 ' i aramak) ve ile birlikte gelen sürümü seçmeniz önemlidir `VS 2019` .
1. Araçları yüklemek için **Değiştir** ' i seçin.

### <a name="on-the-remote-machine"></a>Uzak makinede

1. Uzak araçları uzak makineye yükler. Bu öğretici için, [Uzak araçları indirme ve yükleme](https://docs.microsoft.com/visualstudio/debugger/remote-debugging-cpp?%23download-and-install-the-remote-tools#download-and-install-the-remote-tools)bölümündeki YÖNERGELERI izleyerek ARM64 araçlarını yükleyin.
1. Uzak makinede uzaktan hata ayıklayıcıyı başlatın ve yapılandırın. Bu öğreticide, uzak Windows makinesinde [Uzaktan hata ayıklayıcıyı ayarlama](https://docs.microsoft.com/visualstudio/debugger/remote-debugging-cpp?%23download-and-install-the-remote-tools#BKMK_setup) yönergelerini izleyerek bunu yapın.

## <a name="create-a-cmake-project"></a>CMake projesi oluşturma

Windows konak makinesinde:
1. Visual Studio 'Yu çalıştırma
1. Ana menüden **Dosya**  >  **Yeni**  >  **Proje**' yi seçin.
1. **CMake projesini**  >  **İleri** Seç
1. Projeye bir ad verin ve bir konum seçin. Ardından **Oluştur**’u seçin.

Projeyi oluşturmak ve **Çözüm Gezgini** doldurmak Için Visual Studio 'yu birkaç dakika sonra sunun.

## <a name="configure-for-arm64"></a>ARM64 için yapılandırma

Bir ARM64 Windows makinesini hedeflemek için ARM64 derleme araçlarını kullanarak derlemeniz gerekir.

Visual Studio **yapılandırma** açılan listesini seçin ve **yapılandırmaları Yönet**' i seçin.

![Visual Studio konfigürasyonları açılır penceresinde konfigürasyonları Yönet ' i seçin](media/vs2019-cmake-manage-configurations.png)

**Yeni yapılandırma** Ekle (yeşil düğme) öğesini seçerek yeni bir yapılandırma ekleyin **+** . \
Görüntülenen **Cmakesettings** iletişim kutusunda **arm64-Debug**' ı seçin ve ardından **Seç**' e basın:

![Arm64-Debug Yapılandırması Ekle](media/cmake-add-config-icon-with-target-dialog.png)

Bu, dosyanıza **arm64-Debug** adlı bir hata ayıklama yapılandırması ekler *`CmakeSettings.json`* . Bu yapılandırma adı, **yapılandırma** açılan listesinde bu ayarları tanımlamanızı kolaylaştıran benzersiz ve kolay bir addır.

**Araç kümesi** açılan kutusu **msvc_arm64_x64** olarak ayarlanır. Ayarlarınız şu şekilde görünmelidir:

![CMake ayarları iletişim kutusu](media/cmake-settings-editor2.png)

> [!Note]
> **Araç kümesi** açılan menüsünde, **msvc_arm64** arm64 'e çapraz derlemek için 32 bitlik konak araçları ' nı seçer **msvc_arm64 x64** , arm64-----------Bu öğreticide yapılacak şekilde 64 bit ana bilgisayar araçlarını seçer.

`CMakeSettings.json` dosyasını kaydedin. Yapılandırma açılan listesinde **arm64-Debug** ' ı seçin (Bu işlem, dosyanın listede görünmesini bir süre sonra devam edebilir `CMakeSettings.json` ):

![Visual Studio yapılandırma açılan penceresinde arm64-Debug ' ın seçildiğinden emin olun](media/vs2019-cmake-manage-configurations-arm.png) 

## <a name="add-a-debug-configuration-file"></a>Hata ayıklama yapılandırma dosyası Ekle

Ardından, Visual Studio 'Nun uzak makinenizi nerede bulacağını belirten yapılandırma bilgilerini ve diğer yapılandırma ayrıntılarını ekleyin.

**Görünümleri** Değiştir düğmesini seçerek **Çözüm Gezgini** görünümünü hedefler görünümü olarak değiştirin:

![Çözüm Gezgini anahtar görünümü düğmesi](media/solution-explorer-switch-view.png)

Ardından, **Çözüm Gezgini**, projeyi görmek Için **CMake hedefleri görünümü** ' ne çift tıklayın.

Proje klasörünü açın (Bu örnekte, **CMakeProject3 projesi**) ve ardından çalıştırılabilire sağ tıklayın ve **hata ayıklama yapılandırması Ekle**' yi seçin:

![Hata ayıklama yapılandırması Ekle 'yi seçin](media/cmake-targets-add-debug-configuration.png)

Bu `launch.vs.json` , projenizde bir dosya oluşturur. Uzaktan hata ayıklamayı etkinleştirmek için açın ve aşağıdaki girişleri değiştirin:

- `projectTarget`: yukarıdaki yönergelere göre **Çözüm Gezgini** hedefleri görünümünden hata ayıklama yapılandırma dosyasını eklediyseniz, bu sizin için ayarlanır.
- `remoteMachineName`: uzak ARM64 makinenin IP adresine veya makine adına ayarlanır.

Ayarlar hakkında daha fazla bilgi için `launch.vs.json` bkz. [ şema başvurusundalaunch.vs.js](launch-vs-schema-reference-cpp.md).

> [!Note]
>  **Çözüm Gezgini** içinde hedefler görünümü yerine klasör görünümünü kullanıyorsanız, dosyaya sağ tıklayın `CMakeLists.txt` ve **hata ayıklama yapılandırması Ekle**' yi seçin. Bu deneyim, aşağıdaki yollarla, hedef görünümünden hata ayıklama yapılandırması eklemekten farklıdır:
> - Bir hata ayıklayıcı seçmeniz istenir (  **C/C++ Uzaktan Windows hata ayıklama** seçeneğini belirleyin).
> - Visual Studio, dosyaya daha az yapılandırma şablonu bilgileri sağlayacaktır, `launch.vs.json` böylece kendiniz eklemeniz gerekir. `remoteMachineName`Ve girdilerini sağlamanız gerekir `projectTarget` . Yapılandırma hedefleri görünümünde eklediğinizde yalnızca belirtmeniz gerekir `remoteMachineName` .
> - `projectTarget`Ayar değeri için, hedefin benzersiz adını (örneğin, bu öğreticide 'CMakeProject3.exe ') almak için başlangıç öğesi açılan listesini denetleyin.

## <a name="start-the-remote-debugger-monitor-on-the-remote-windows-machine"></a>Uzak Windows makinesinde uzaktan hata ayıklayıcı İzleyicisini Başlat

CMake projenizi çalıştırmadan önce, Visual Studio 2019 uzaktan hata ayıklayıcı 'nın uzak Windows makinesinde çalıştığından emin olun.  Kimlik doğrulama durumunuza bağlı olarak uzaktan hata ayıklayıcı seçeneklerini değiştirmeniz gerekebilir.

Örneğin, uzak makinede, Visual Studio uzaktan hata ayıklayıcı menü çubuğundan **Araçlar**  >  **Seçenekler**' i seçin. **Kimlik doğrulama modunu** ortamınızın nasıl ayarlanacağını eşleşecek şekilde ayarlayın:

![Uzaktan hata ayıklayıcı kimlik doğrulama seçenekleri](media/remote-debugger-options.png)

Ardından, ana makinedeki Visual Studio 'da, `launch.vs.json` eşleşecek dosyayı güncelleştirin. Örneğin, uzaktan hata ayıklayıcı 'da **kimlik doğrulaması yok** ' u seçerseniz, `launch.vs.json` bölümüne **"AuthenticationType": "none"** ekleyerek projenizdeki dosyayı güncelleştirin `configurations` `launch.vs.json` . Aksi takdirde, `"authenticationType"` Varsayılan olarak öğesine `"windows"` ve açıkça belirtilmesi gerekmez. Bu örnek, `launch.vs.json` kimlik doğrulaması için yapılandırılmış bir dosyayı gösterir:

``` XAML
{
  "version": "0.2.1",
  "defaults": {},
  "configurations": [
    {
        "type": "remoteWindows",
        "authenticationType": "none"
        "name": "CMakeLists.txt",
        "project": "CMakeLists.txt",
        "projectTarget": "CMakeProject3.exe",
        "remoteMachineName": "<ip address goes here>",
        "cwd": "${debugInfo.defaultWorkingDirectory}",
        "program": "${debugInfo.fullTargetPath}",
        "deploy": [],
        "args": [],
        "env": {}
    },
    {
      "type": "default",
      "project": "CMakeLists.txt",
      "projectTarget": "CMakeProject3.exe",
      "name": "CMakeProject3.exe"
    }
  ]
}
```

## <a name="debug-the-app"></a>Uygulamada hata ayıklama

Konak makinede, Visual Studio **Çözüm Gezgini**, CMake PROJENIZ için cpp dosyasını açın. Hala **CMake hedefleri görünümünde** çalışıyorsanız, onu görmek için **(yürütülebilir)** düğümünü açmanız gerekir.

Varsayılan CPP dosyası basit bir Hello World konsol uygulamasıdır. Üzerinde bir kesme noktası ayarlayın `return 0;` .

Visual Studio araç çubuğunda, dosyanızda belirttiğiniz adı seçmek için **Başlangıç öğesi** açılan listesini kullanın `"name"` `launch.vs.json` :

![CMakeProject3.exe seçili olan örnek başlangıç öğesi açılan kutusu](media/startup-item.png)

Hata ayıklamayı başlatmak için, Visual Studio araç çubuğunda Hata **ayıklama**  >  **Başlat hata ayıklamayı** seçin (veya **F5** tuşuna basın).

Başlamazsa, aşağıdakilerin dosyada doğru şekilde ayarlandığından emin olun `launch.vs.json` :
- `"remoteMachineName"` , uzak ARM64 Windows makinenin IP adresine veya makine adına ayarlanmalıdır.
- `"name"` Visual Studio başlangıç öğesi açılan menüsünde seçimle eşleşmelidir.
- `"projectTarget"` hata ayıklamak istediğiniz CMake hedefinin adıyla eşleşmelidir.
- `"type"` olmalıdır `"remoteWindows"`
- Uzaktan hata ayıklayıcı 'daki kimlik doğrulama türü **kimlik doğrulaması olmadan** ayarlandıysa, `"authenticationType": "none"` dosyasında ayarlamış olmanız gerekir `launch.vs.json` .
- Windows kimlik doğrulaması kullanıyorsanız, uzak makine tarafından tanınan bir hesap kullanarak istendiğinde oturum açın.

Proje oluşturulduktan sonra, uygulamanın uzak ARM64 Windows makinesinde görünmesi gerekir:

![Merhaba CMake konsol uygulaması uzak Windows ARM64 makinesinde çalışıyor](media/remote-cmake-app.png)

Ana makinedeki Visual Studio, için kesme noktasında durdurulmalıdır `return 0;` .

## <a name="what-you-learned"></a>Öğrendikleriniz

Bu öğreticide, bir CMake projesi oluşturdunuz, bunu ARM64 üzerinde Windows için derlemek üzere yapılandırdınız ve bir uzak ARM64 Windows makinesinde hata ayıklaması yaparsınız.

## <a name="next-steps"></a>Sonraki adımlar

Visual Studio 'da CMake projelerini yapılandırma ve hata ayıklama hakkında daha fazla bilgi edinin:

> [!div class="nextstepaction"]
> [Visual Studio 'da CMake projeleri](cmake-projects-in-visual-studio.md)\
> [CMake derleme ayarlarını özelleştirme](customize-cmake-settings.md)\
> [CMake hata ayıklama oturumlarını yapılandırma](configure-cmake-debugging-sessions.md)\
> [CMake önceden tanımlanmış yapılandırma başvurusu](cmake-predefined-configuration-reference.md)\
[ Şema başvurusundalaunch.vs.js](launch-vs-schema-reference-cpp.md)
