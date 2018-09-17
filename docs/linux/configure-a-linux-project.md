---
title: Visual Studio'da C++ Linux projesi yapılandırma | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-linux
ms.tgt_pltfrm: Linux
ms.topic: conceptual
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- linux
ms.openlocfilehash: a66e2f6b6506d995859c89d9588b59056047220e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45713589"
---
# <a name="configure-a-linux-project"></a>Linux projesi yapılandırma

Bu konuda, Visual Studio'da C++ Linux projesi yapılandırma açıklar. Visual Studio'da CMake Linux projeleri hakkında daha fazla bilgi için bkz: [Linux CMake projesi yapılandırma ](cmake-linux-project.md).

## <a name="general-settings"></a>Genel ayarlar

Visual Studio ile Linux projesi için çeşitli seçenekler yapılandırılabilir.  Bu seçenekleri görüntülemek için seçin **Proje > Özellikleri** menüsü ya da projeye sağ tıklayarak **Çözüm Gezgini** seçip **özellikleri** bağlam menüsünden. **Genel** ayarları görüntülenir.

![Genel yapılandırma](media/settings_general.png)

Varsayılan olarak, bir yürütülebilir dosya (.out) aracı ile yerleşik hale getirilmiştir.  Bir statik veya dinamik kitaplığını oluşturmak veya mevcut bir derleme görevleri dosyası kullanmak için **yapılandırma türü** seçimi.

## <a name="remote-settings"></a>Uzak bağlantı ayarları

Uzak Linux bilgisayara ilgili ayarları değiştirmek için görünen Uzak seçenekleri yapılandırma **genel** ayarları:

- Hedef Linux bilgisayarı değiştirmek için kullanın **uzak derleme makinesi** girişi.  Bu, daha önce oluşturduğunuz bağlantılardan birini seçmenize olanak sağlar.  Yeni bir giriş oluşturmak için lütfen bkz [için Uzak Linux bilgisayarınıza bağlanma](connect-to-your-remote-linux-computer.md) bölümü.

- **Uzaktan derleme kök dizini** proje uzak Linux bilgisayarda nerede oluşturulan kök konumu belirler.  Bu varsayılan **~/projects** değiştirmediğiniz sürece.

- **Uzaktan derleme proje dizini** burada uzak Linux bilgisayarda bu belirli proje oluşturulacak olan.  Bu varsayılan **$(RemoteRootDir)/$(ProjectName)**, yukarıda kök dizininin altındaki şu anki proje sonra adlandırılmış bir dizine genişletin.

> [!NOTE]
> ' % S'varsayılan C ve C++ Derleyicileri, veya bağlayıcı ve projeyi derlemek için kullanılan Arşivleyicide değiştirmek için uygun girdileri kullanmak **C/C++ > Genel** bölümü ve **bağlayıcı > Genel** bölümü.  Bunlar, örneğin belirli bir sürümü GCC veya hatta Clang derleyici kullanmak için ayarlanabilir.

## <a name="include-directories-and-intellisense-support"></a>Dizinleri ve IntelliSense desteğini içerir

**Visual Studio 2017 sürüm 15.6 ve önceki sürümler:**<br/>
Varsayılan olarak, Visual Studio sistem düzeyindeki içerik dosyalarını Linux bilgisayardan içermez.  Örneğin, öğeler **/usr/INCLUDE** dizini Visual Studio'da mevcut değildir.
Tam [IntelliSense](/visualstudio/ide/using-intellisense) desteği gerekir, geliştirme bilgisayarınızdaki bir konuma dosyaları kopyalayın ve Visual Studio bu konuma işaret edecek.  Bir seçenek, dosyaları kopyalamak için SCP'yi (güvenli kopya) kullanmaktır.  Windows 10'da kullandığınız [Windows üzerinde Bash](https://msdn.microsoft.com/commandline/wsl/about) scp çalıştırılacak.  Önceki Windows sürümleri için aşağıdaki gibi kullanabilirsiniz [PSCP'yi (PuTTY güvenli kopya)](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html).

Aşağıdakine benzer bir komut kullanarak dosyalarını kopyalayabilirsiniz:

`scp -r linux_username@remote_host:/usr/include .`

Elbette, değiştirin **linux_username** ve **remote_host** değerleri üzerinde nelerin kendi ortamınızda uygun olduğu için.

Dosyalar kopyalandıktan sonra kullanmak **VC ++ dizinleri** Visual Studio yalnızca kopyalanan ek içerme dosyaları nerede bulacağını bildirmek için proje özelliklerinde öğesi.

![VC ++ dizinleri](media/settings_directories.png)

**Visual Studio 2017 sürüm 15.7 ve üzeri:**<br/>
Bkz: [uzak üst bilgiler için IntelliSense yönetme](#remote_intellisense).

## <a name="copy-sources"></a>Kaynakları Kopyala

Oluştururken, kaynak dosyaları PC geliştirme Linux bilgisayara kopyalar ve orada derlenir.  Varsayılan olarak, tüm kaynakları Visual Studio projesini, yukarıdaki ayarlarında belirlenen konumlara kopyalanır.  Ancak, ek kaynaklar listesine de eklenebilir veya kaynakları kopyalama bir derleme görevleri dosyası projesi için varsayılan seçenek tamamen devre dışı kapatılabilir.

- **Kopyalanacak kaynakları** hangi kaynakları uzak bilgisayara kopyalanır belirler.  Varsayılan olarak,  **\@(SourcesToCopyRemotely)** projedeki tüm kaynak kodu dosyaları için varsayılan olarak, ancak resimler gibi herhangi bir varlık/kaynak dosyası içermiyor.

- **Kaynakları Kopyala** açılabilir ve etkinleştirmek ve uzak bilgisayarın kaynak dosyaların kopyalanmasını devre dışı bırakmak için kapalı.

- **Kopyalanacak ek kaynakları** uzak sisteme kopyalanacak ek kaynak dosyaları eklemenizi sağlar.  Noktalı virgülle ayrılmış liste belirtebilir veya kullanabileceğiniz **: =** kullanılacak yerel ve uzak bir ad belirtmek için sözdizimi:

`C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Derleme olayları

Tüm derleme bir uzak bilgisayarda gerçekleştiği için birkaç ek derleme olayları proje özelliklerinde Build Events bölümüne eklenmiştir.  Bunlar **uzaktan derleme öncesi olay**, **uzaktan bağlama öncesi olay**, ve **uzaktan derleme sonrası olay**ve uzak bilgisayarda önce veya sonra tek tek adımları meydana gelir işlemi.

![Derleme olayları](media/settings_buildevents.png)

## <a name="remote_intellisense"></a> Uzak üst bilgiler (Visual Studio 2017 sürüm 15.7 ve üzeri) için IntelliSense

İçinde yeni bir bağlantı eklediğinizde **Bağlantı Yöneticisi**, Visual Studio uzak sistem üzerindeki derleyici için dizinleri otomatik olarak algılar. Visual Studio sonra zıps ve bu dosyaların yerel Windows makinenizde bir dizine kopyalar. Her bir Visual Studio ya da CMake proje bu bağlantının kullandığınızda bundan sonra bu dizinlerin üstbilgilerinde IntelliSense sağlamak için kullanılır.

Bu işlev, zip yüklü olan bir Linux makinesinde bağlıdır. Zip bu apt-get komutuyla yükleyebilirsiniz:

```cmd
apt install zip
```

Üst bilgi önbelleği yönetmek için gidin **Araçlar > Seçenekler, Çoklu Platform > Bağlantı Yöneticisi > Uzak üst bilgiler IntelliSense Yöneticisi**. Linux makinenizde değişiklikleri yaptıktan sonra üst bilgi önbelleği güncelleştirmek için Uzak bağlantıyı seçin ve ardından **güncelleştirme**. Seçin **Sil** bağlantı silmeden üstbilgileri kaldırmak için. Seçin **Araştır** yerel dizinde açmak için **dosya Gezgini**. Bu klasör, salt okunur olarak kabul eder. 15.3 sürümü önce oluşturulmuş mevcut bir bağlantı için üst bilgileri indirmek için Bağlan'ı seçin ve ardından **indirme**.

![Uzak üst bilgi IntelliSense](media/remote-header-intellisense.png)

## <a name="see-also"></a>Ayrıca Bkz.

[Proje Özellikleriyle Çalışma](../ide/working-with-project-properties.md)  
[C++ genel özellikleri (Linux C++)](../linux/prop-pages/general-linux.md)  
[VC ++ dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md)  
[Kopyalama kaynakları proje özellikleri (Linux C++)](../linux/prop-pages/copy-sources-project.md)  
[Derleme olay özellikleri (Linux C++)](../linux/prop-pages/build-events-linux.md)