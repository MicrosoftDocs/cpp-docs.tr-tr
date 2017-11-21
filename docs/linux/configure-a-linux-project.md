---
title: "Visual Studio'da C++ Linux projesi yapılandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/15/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-linux
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d7c6adf-54b9-4b23-bd23-5de0c825b768
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e727f4588c425e3a6c94d7ceb09ebc8d494e24cf
ms.sourcegitcommit: 1b480aa74886930b3bd0435d71cfcc3ccda36424
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2017
---
# <a name="configure-a-linux-project"></a>Bir Linux proje yapılandırma
Bu konuda, bir Visual Studio Linux proje yapılandırma açıklar. CMake Linux projeler hakkında daha fazla bilgi için bkz: [bir Linux CMake proje yapılandırma ](cmake-linux-project.md).

## <a name="general-settings"></a>Genel ayarları
Visual Studio ile Linux projesi için çeşitli seçenekler yapılandırılabilir.  Bu seçenekleri görüntülemek için seçin **Proje > Özellikler** menüsü veya projeye sağ tıklayarak **Çözüm Gezgini** seçip **özellikleri** ve bağlam menüsünden. **Genel** ayarları görüntülenir.

![Genel yapılandırma](media/settings_general.png)

Varsayılan olarak, bir yürütülebilir dosya (.out) aracıyla yerleşik olarak bulunur.  Statik veya dinamik kitaplığını oluşturmak veya var olan bir derleme görevleri dosyası kullanmak için **yapılandırma türü** seçim.

## <a name="remote-settings"></a>Uzak bağlantı ayarları
Uzak Linux bilgisayara ilgili ayarları değiştirmek için görünür uzaktan seçenekleri yapılandırmak **genel** ayarları:

* Hedef Linux bilgisayarı değiştirmek için kullanın **uzak yapı makine** girişi.  Bu, daha önce oluşturduğunuz bağlantılardan birini seçmenize olanak sağlar.  Yeni bir giriş oluşturmak için lütfen bkz [bilgisayarınızı uzaktan Linux bilgisayara bağlanmayı](connect-to-your-remote-linux-computer.md) bölümü.

* **Uzak yapı kök dizin** projeyi uzak Linux bilgisayarda nerede oluşturulmuştur, kök konumunu belirler.  Bu varsayılan **~/projects** değiştirmediyse.

* **Uzak yapı proje dizini** bu belirli bir proje uzak Linux bilgisayarda nerede oluşturulacak olan.  Bu varsayılan **$(RemoteRootDir)/$(ProjectName)**, yukarıda belirlenen kök dizininin altında geçerli projenin sonra adlandırılmış bir dizine genişletin.

> [!NOTE]
> Varsayılan C ve C++ Derleyicileri veya bağlayıcı ve projeyi oluşturmak için kullanılan Archiver değiştirmek için uygun girdileri kullanmak **C/C++ > Genel** bölüm ve **bağlayıcı > Genel** bölümü.  Bu belirli sürümü GCC veya hatta Clang derleyici örneğin kullanmak üzere ayarlanabilir.

## <a name="vc-directories"></a>VC ++ dizinleri
Varsayılan olarak, Visual Studio sistem düzeyinde INCLUDE dosyalarla Linux bilgisayardan içermez.  Örneğin, öğeler **/usr/INCLUDE** dizin Visual Studio'da mevcut değildir.  Tam için [IntelliSense](/visualstudio/ide/using-intellisense) desteği gerekir bu dosyalarını geliştirme bilgisayarınızda bazı konuma kopyalayın ve Visual Studio bu konuma gelin.  Dosyaları kopyalamak için scp (güvenli kopya) kullanan bir seçenektir.  Windows 10, kullandığınız [Bash Windows](https://msdn.microsoft.com/commandline/wsl/about) scp çalıştırmak için.  Önceki Windows sürümleri için aşağıdakine benzer kullanabilirsiniz [PSCP (PuTTY güvenli kopya)](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html).

Aşağıdakine benzer bir komut kullanarak dosyaları kopyalayabilirsiniz:

`scp -r linux_username@remote_host:/usr/include .`

Elbette, yerini **linux_username** ve **remote_host** değerleri yukarıda ne kendi ortamınıza uygun içindir.

Dosyaları kopyaladıktan sonra kullanmak **VC ++ dizinleri** öğesi proje özelliklerinde hemen kopyalanan ek dosyaları nerede bulacağını Visual Studio bildirir.

![VC ++ dizinleri](media/settings_directories.png)

## <a name="copy-sources"></a>Kaynakları kopyalama
Oluştururken, PC geliştirme kaynak dosyalara Linux bilgisayara kopyalanır ve derlenmiş vardır.  Varsayılan olarak, tüm kaynakları Visual Studio Proje Ayarları'nda yukarıdaki konumlara kopyalanır.  Ancak, ek kaynaklar listesine de eklenebilir veya kaynakları kopyalama derleme görevleri dosyası projesi için varsayılan olan tamamen devre dışı açılabilir.

* **Kaynakları kopyalamak için** hangi kaynakları uzak bilgisayara kopyalanır belirler.  Varsayılan olarak, **@(SourcesToCopyRemotely)** projedeki tüm kaynak kodu dosyaları varsayılan olarak, ancak görüntüleri gibi herhangi bir varlık/kaynak dosyalarını içermez.

* **Kaynakları kopyalamak** açılabilir ve etkinleştirmek ve kaynak dosyalarının uzak bilgisayara kopyalama devre dışı bırakmak için kapalı.

* **Kopyalamak için ek kaynaklar** uzak sisteme kopyalanacak ek kaynak dosyalarını eklemenizi sağlar.  Noktalı virgülle ayrılmış listesini belirtebilir veya kullanabileceğiniz **: =** sözdizimi kullanılacak yerel ve uzak bir ad belirtin:

  `C:\Projects\ConsoleApplication1\MyFile.cpp:=~/projects/ConsoleApplication1/ADifferentName.cpp;C:\Projects\ConsoleApplication1\MyFile2.cpp:=~/projects/ConsoleApplication1/ADifferentName2.cpp;`

## <a name="build-events"></a>Derleme olayları
Tüm derleme bir uzak bilgisayarda gerçekleştiği için birkaç ek yapı olayları Proje Özellikleri'nde yapı olayları bölümüne eklenmiştir.  Bunlar **uzak oluşturma öncesi olay**, **uzak bağlama öncesi olay**, ve **uzak oluşturma sonrası olay**ve uzak bilgisayarda önce veya tek tek adımları sonra gerçekleşir işlemi.

![Derleme olayları](media/settings_buildevents.png)

## <a name="see-also"></a>Ayrıca Bkz.
[Proje özellikleriyle çalışma](../ide/working-with-project-properties.md)  
[C++ genel özellikleri (Linux C++)](../linux/prop-pages/general-linux.md)  
[VC ++ dizinleri (Linux C++)](../linux/prop-pages/directories-linux.md)  
[Proje Özellikleri (Linux C++) kopyalama kaynakları](../linux/prop-pages/copy-sources-project.md)  
[Yapı olay özellikleri (Linux C++)](../linux/prop-pages/build-events-linux.md)