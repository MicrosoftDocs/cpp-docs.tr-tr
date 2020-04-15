---
title: Visual Studio'da C++ Linux projenizi dağıtın, çalıştırın ve hata ayıklama
description: Visual Studio'daki bir Linux C++ projesinin içinden uzak hedefteki kodunasıl derleyip, çalıştırıp hata ayıklanınca anlatılır.
ms.date: 06/07/2019
ms.assetid: f7084cdb-17b1-4960-b522-f84981bea879
ms.openlocfilehash: e68feab3a71cd5bb3f6b88eee52f0872ef4bb213
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "80077834"
---
# <a name="deploy-run-and-debug-your-linux-project"></a>Linux projenizi dağıtma, çalıştırma ve projenizin hatalarını ayıklama

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

Visual Studio'da bir Linux C++ projesi oluşturduktan ve [Linux Bağlantı Yöneticisi'ni](connect-to-your-remote-linux-computer.md)kullanarak projeye bağlandıktan sonra, projeyi çalıştırıp hata ayıklayabilirsiniz. Uzak hedefteki kodu derler, çalıştırın ve hata ayıklarsınız.

::: moniker range="vs-2019"

**Visual Studio 2019 sürüm 16.1** Hata ayıklama ve oluşturma için farklı Linux sistemlerini hedefleyebilirsiniz. Örneğin, X64'te çapraz derleme yapabilir ve IoT senaryolarını hedefalırken arm aygıtına dağıtabilirsiniz. Daha fazla bilgi için, bu makalenin ilerleyen saatlerinde [bina ve hata ayıklama için farklı makineleri belirt'e](#separate_build_debug) bakın.

::: moniker-end

Linux projenizle etkileşim kurmanın ve hata ayıklamanın çeşitli yolları vardır.

- Kesme noktaları, saat pencereleri ve bir değişkenin üzerinde gezinme gibi geleneksel Visual Studio özelliklerini kullanarak hata ayıklama. Bu yöntemleri kullanarak, normalde diğer proje türleri için olduğu gibi hata ayıklama olabilir.

- Linux Console penceresindeki hedef bilgisayardan çıktıgörüntüleyin. Konsolu hedef bilgisayara giriş göndermek için de kullanabilirsiniz.

## <a name="debug-your-linux-project"></a>Linux projenizi hata ayıklama

1. **Hata ayıklama** özelliği sayfasında hata ayıklama modunu seçin.

   ::: moniker range="vs-2019"

   GDB, Linux üzerinde çalışan uygulamaları hata ayıklamak için kullanılır. Uzak bir sistemde hata ayıklama yaparken (WSL değil) GDB, projenin Hata **Ayıklama** özelliği sayfasındaki **Hata Ayıklama Modu** seçeneğinden seçilebilen iki farklı modda çalıştırılabilir:

   ![GDB seçenekleri](media/vs2019-debugger-settings.png)

   ::: moniker-end

   ::: moniker range="vs-2017"

   GDB, Linux üzerinde çalışan uygulamaları hata ayıklamak için kullanılır. GDB, projenin Hata **Ayıklama** özelliği sayfasındaki **Hata Ayıklama Modu** seçeneğinden seçilebilen iki farklı modda çalıştırılabilir:

   ![GDB seçenekleri](media/vs2017-debugger-settings.png)

   ::: moniker-end

   - **GDBServer** modunda, GDB uzak sistemdeki gdbserver'a bağlanan yerel olarak çalıştırılır.  Bunun Linux Console penceresinin desteklediği tek mod olduğunu unutmayın.

   - **GDB** modunda, Visual Studio hata ayıklama uzak sistemde GDB sürücüler. GDB'nin yerel sürümü hedef bilgisayara yüklenen sürümle uyumlu değilse, bu daha iyi bir seçenektir. |

   > [!NOTE]
   > gdbserver hata ayıklama modunda kesme noktalarına ulaşamıyorsanız, gdb modunu deneyin. gdb öncelikle uzak hedefe [kurulmalıdır.](download-install-and-setup-the-linux-development-workload.md)

1. Visual Studio'daki standart **Hata Ayıklama** araç çubuğunu kullanarak uzak hedefi seçin.

   Uzak hedef kullanılabilir olduğunda, bu hedefin ad veya IP adresi tarafından listelenmiş olduğunu görürsünüz.

   ![Uzak hedef](media/remote_target.png)

   Henüz uzak hedefe bağlı değilseniz, uzak hedefe bağlanmak için [Linux Connection Manager'ı](connect-to-your-remote-linux-computer.md) kullanma talimatı görürsünüz.

   ![Uzak Mimari](media/architecture.png)

1. Yürüteceğini bildiğiniz bazı kodların sol oluk'una tıklayarak bir kesme noktası ayarlayın.

   Kesme noktasını ayarladığınız kod satırında kırmızı bir nokta görüntülenir.

1. Hata ayıklamaya başlamak için **F5** (veya **Hata Ayıklama > Hata Ayıklama'ya**başlayın).

   Hata ayıklamaya başladığınızda, uygulama başlamadan önce uzak hedefte derlenir. Tüm derleme hataları Hata **Listesi** penceresinde görünür.

   Hata yoksa, uygulama başlatılır ve hata ayıklama kesme noktasında duraklar.

   ![Bir kesme noktasına çarptım](media/hit_breakpoint.png)

   Şimdi, uygulamayla geçerli durumunda etkileşimkurabilir, değişkenleri görüntüleyebilir ve **F10** veya **F11**gibi komut tuşlarına basarak kod üzerinden adım atabilirsiniz.

1. Uygulamanızla etkileşimkurmak için Linux Konsolu'nu kullanmak istiyorsanız, **Hata Ayıklama > Linux Konsolu'nu**seçin.

   ![Linux Konsol uçağı menüsü](media/consolemenu.png)

   Bu konsol, hedef bilgisayardan herhangi bir konsol çıktısını görüntüleyecek ve girdi alıp hedef bilgisayara gönderecek.

   ![Linux Konsol penceresi](media/consolewindow.png)

## <a name="configure-other-debugging-options-msbuild-based-projects"></a>Diğer hata ayıklama seçeneklerini yapılandırma (MSBuild tabanlı projeler)

- Komut satırı bağımsız değişkenleri, projenin **Hata Ayıklama** özelliği sayfasındaki **Program Bağımsız Değişkenleri** öğesi kullanılarak yürütülebilir bağımsız değişkenlere geçirilebilir.

   ![Program Bağımsız Değişkenleri](media/settings_programarguments.png)

- Belirli hata ayıklama seçenekleri **Ek Hata Ayıklama Komutları** girişi kullanılarak GDB'ye geçirilebilir.  Örneğin, SIGILL (yasadışı talimat) sinyallerini yok saymak isteyebilirsiniz.  Yukarıda gösterildiği gibi **Ek Hata Ayıklama Komutları** girişine aşağıdakileri ekleyerek bunu başarmak için **tutamak** komutunu kullanabilirsiniz:

   `handle SIGILL nostop noprint`

## <a name="configure-other-debugging-options-cmake-projects"></a>Diğer hata ayıklama seçeneklerini yapılandırma (CMake projeleri)

Launch.vs.json dosyasında bir CMake projesi için ek komut satırı bağımsız değişkenleri belirtebilirsiniz. Daha fazla bilgi için [Bkz. CMake projesi hata ayıklama](cmake-linux-project.md#debug_cmake_project)

## <a name="debug-with-attach-to-process"></a>İşleme Ekle ile Hata Ayıklama

Visual Studio projeleri için [Hata Ayıklama](prop-pages/debugging-linux.md) özelliği sayfası ve CMake projeleri için **Launch.vs.json** ayarları, çalışan bir işleme eklemenizi sağlayan ayarlara sahiptir. Bu ayarlarda sağlananın ötesinde ek denetime ihtiyaç duyarsanız, çözümünüzün veya çalışma alanınızın köküne adlandırılmış `Microsoft.MIEngine.Options.xml` bir dosya yerleştirebilirsiniz. İşte basit bir örnek:

```xml
<?xml version="1.0" encoding="utf-8"?>
<SupplementalLaunchOptions>
    <AttachOptions>
      <AttachOptionsForConnection AdditionalSOLibSearchPath="/home/user/solibs">
        <ServerOptions MIDebuggerPath="C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise\Common7\IDE\VC\Linux\bin\gdb\7.9\x86_64-linux-gnu-gdb.exe"
ExePath="C:\temp\ConsoleApplication17\ConsoleApplication17\bin\x64\Debug\ConsoleApplication17.out"/>
        <SetupCommands>
          <Command IgnoreFailures="true">-enable-pretty-printing</Command>
        </SetupCommands>
      </AttachOptionsForConnection>
    </AttachOptions>
</SupplementalLaunchOptions>
```

**AttachOptionsForConnection,** gereksinim duyabileceğiniz özniteliklerin çoğuna sahiptir. Yukarıdaki örnekte, ek .so kitaplıklarını aramak için bir konum nasıl belirtilir gösterilmektedir. Alt öğe **ServerOptions** yerine gdbserver ile uzak işleme ekleme sağlar. Bunu yapmak için yerel bir gdb istemcisi (Visual Studio 2017'de gönderilen istemci yukarıda gösterilmiştir) ve sembollerle ikilinin yerel bir kopyasını belirtmeniz gerekir. **SetupCommands** öğesi komutları doğrudan gdb'ye geçirmenizi sağlar. GitHub'daki [LaunchOptions.xsd şemasında](https://github.com/Microsoft/MIEngine/blob/master/src/MICore/LaunchOptions.xsd) bulunan tüm seçenekleri bulabilirsiniz.

::: moniker range="vs-2019"

## <a name="specify-different-machines-for-building-and-debugging"></a><a name="separate_build_debug"></a>Bina ve hata ayıklama için farklı makineleri belirtin

Visual Studio 2019 sürüm 16.1'de, uzaktan yapı makinenizi hem MSBuild tabanlı Linux projeleri hem de uzak bir Linux makinesini hedefleyen CMake projeleri için uzaktan hata ayıklama makinenizden ayırabilirsiniz. Örneğin, artık x64'te çapraz derleme yapabilir ve IoT senaryolarını hedeflerken arm aygıtına dağıtabilirsiniz.

### <a name="msbuild-based-projects"></a>MSBuild tabanlı projeler

Varsayılan olarak, uzaktan hata ayıklama makinesi uzaktan yapı makinesi **(Configuration Properties** > **General** > **Remote Build Machine)** ile aynıdır. Yeni bir uzaktan hata ayıklama makinesi belirtmek **için, Solution Explorer'daki** projeye sağ tıklayın ve**Uzaktan Hata Ayıklama** **Makinesi'ni** > **Ayıklama** > Yapılandırma Özellikleri'ne gidin.  

![Linux uzaktan hata ayıklama makinesi](media/linux-remote-debug-machine.png)

**Uzaktan Hata Ayıklama Makinesi** için açılır menü, kurulan tüm uzak bağlantılarla doldurulur. Yeni bir uzaktan bağlantı eklemek **için, Araçlar** > **Seçenekleri** > **Çapraz Platform** > **Bağlantı Yöneticisi'ne** gidin veya **Hızlı Başlatma'da**"Bağlantı Yöneticisi"ni arayın. Ayrıca projenin Özellik Sayfalarında yeni bir uzaktan dağıtma dizini **(Configuration Properties** > **General** > **Remote Deploy Directory)** de belirtebilirsiniz.

Varsayılan olarak, yalnızca işlemin hata ayıklama için gerekli dosyaları uzak hata ayıklama makinesine dağıtılır. Uzak hata ayıklama makinesine hangi kaynak dosyaların dağıtılacağını yapılandırmak için **Solution Explorer'ı** kullanabilirsiniz. Bir kaynak dosyayı tıklattığınızda, Dosya Özelliklerinin önizlemesini doğrudan Çözüm Gezgini'nin altında görürsünüz.

![Linux dağıtılabilir dosyalar](media/linux-deployable-content.png)

**İçerik** özelliği, dosyanın uzaktan hata ayıklama makinesine dağıtılıp dağıtılmayacağını belirtir. **Özellik Sayfaları** > **Yapılandırma Yöneticisi'nde** gezinme ve istenen yapılandırma için **Dağıt'ın** denetimini geri alarak dağıtımı tamamen devre dışı kullanabilirsiniz.

Bazı durumlarda, projenizin dağıtımı üzerinde daha fazla denetim eihtiyacınız olabilir. Örneğin, dağıtmak istediğiniz bazı dosyalar çözümünüzün dışında olabilir veya dosya veya dizini başına uzaktan dağıtma dizininizi özelleştirmek istiyorsunuz. Bu gibi durumlarda, .vcxproj dosyanıza aşağıdaki kod bloğu(lar)ı ekleyip "example.cpp"i gerçek dosya adlarıyla değiştirin:

```xml

<ItemGroup>
   <RemoteDeploy Include="__example.cpp">
<!-- This is the source Linux machine, can be empty if DeploymentType is LocalRemote -->
      <SourceMachine>$(RemoteTarget)</SourceMachine>
      <TargetMachine>$(RemoteDebuggingTarget)</TargetMachine>
      <SourcePath>~/example.cpp</SourcePath>
      <TargetPath>~/example.cpp</TargetPath>
<!-- DeploymentType can be LocalRemote, in which case SourceMachine will be empty and SourcePath is a local file on Windows -->
      <DeploymentType>RemoteRemote</DeploymentType>
<!-- Indicates whether the deployment contains executables -->
      <Executable>true</Executable>
   </RemoteDeploy>
</ItemGroup>
```

### <a name="cmake-projects"></a>CMake projeleri

Uzak bir Linux makinesini hedefleyen CMake projeleri için, başlatılınca yeni bir uzaktan hata ayıklama makinesi belirtebilirsiniz.vs.json. Varsayılan olarak, "remoteMachineName" değeri CMakeSettings.json'daki "remoteMachineName" özelliğiyle senkronize edilir ve bu da uzaktan yapı makinenize karşılık gelir. Bu özellikler artık eşleşmek gerekmez ve launch.vs.json'daki "remoteMachineName" değeri dağıtma ve hata ayıklama için hangi uzak makinenin kullanılacağını belirler.

![CMake uzaktan hata ayıklama makinesi](media/cmake-remote-debug-machine.png)

IntelliSense tüm kurulan uzak bağlantıların bir listesini önerecektir. **Araçlar** > **Seçenekleri** > **Çapraz Platform** > **Bağlantı Yöneticisi'ne** yönlendirerek veya **Hızlı Başlatma'da**"Bağlantı Yöneticisi"ni arayarak yeni bir uzaktan bağlantı ekleyebilirsiniz.

Dağıtımınız üzerinde tam denetim istiyorsanız, launch.vs.json dosyasına aşağıdaki kod bloğu(lar)ı ekleyebilirsiniz. Yer tutucu değerlerini gerçek değerlerle değiştirmeyi unutmayın:

```json

"disableDeploy": false,
"deployDirectory": "~\foo",
"deploy" : [
   {
      "sourceMachine": "127.0.0.1 (username=example1, port=22, authentication=Password)",
      "targetMachine": "192.0.0.1 (username=example2, port=22, authentication=Password)",
      "sourcePath": "~/example.cpp",
      "targetPath": "~/example.cpp",
      "executable": "false"
   }
]

```

::: moniker-end

## <a name="next-steps"></a>Sonraki adımlar

- Linux'taki ARM aygıtlarını hata ayıklamak için şu blog gönderisine bakın: [Visual Studio'da gömülü bir ARM cihazının hata ayıklanması.](https://blogs.msdn.microsoft.com/vcblog/2018/01/10/debugging-an-embedded-arm-device-in-visual-studio/)

## <a name="see-also"></a>Ayrıca bkz.

[C++ Hata Ayıklama Özellikleri (Linux C++)](prop-pages/debugging-linux.md)
