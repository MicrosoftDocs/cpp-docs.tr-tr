---
title: 'vcpkg: Windows, Linux ve MacOS için C++ Paket Yöneticisi'
description: vcpkg, Windows, MacOS ve Linux 'ta açık kaynaklı C++ kitaplıklarının alımı ve yüklemesini büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir.
ms.date: 01/10/2020
ms.technology: cpp-ide
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.openlocfilehash: 9dbeba1f55164ace01fb8bb26155dd9319ba62db
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335401"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Windows, Linux ve MacOS için C++ Paket Yöneticisi

vcpkg, C++ için bir komut satırı paket yöneticisidir. Windows, Linux ve MacOS 'ta üçüncü taraf kitaplıkların Alım ve yükleme işlemlerini büyük ölçüde basitleştirir. Projeniz üçüncü taraf kitaplıklar kullanıyorsa, bunları yüklemek için vcpkg kullanmanızı öneririz. vcpkg hem açık kaynaklı hem de özel kitaplıkları destekler. Vcpkg Windows kataloğundaki tüm kitaplıklar, Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 uyumluluğu için test edilmiştir. Windows ve Linux/MacOS katalogları arasında vcpkg artık 1900 ' den fazla kitaplığı desteklemektedir. C++ topluluğu, her iki katalogda de sürekli olarak daha fazla kitaplık ekliyor.

## <a name="simple-yet-flexible"></a>Basit ancak esnek

Tek bir komutla kaynakları indirebilir ve bir kitaplık oluşturabilirsiniz. vcpkg, GitHub 'da bulunan açık kaynaklı bir projem. Özel vcpkg klonlarınızı dilediğiniz şekilde özelleştirmek mümkündür. Örneğin, genel katalogda bulunanlara göre farklı kitaplıklar ya da kitaplıkların farklı sürümlerini belirtin. Tek bir makineye birden fazla vcpkg klonda sahip olabilirsiniz. Her biri, tercih ettiğiniz derleme anahtarlarınız ile özel bir kitaplık koleksiyonu oluşturmak üzere ayarlanabilir. Her kopya, kendi kendi hiyerarşisinde çalışan vcpkg. exe kopyasının bulunduğu kendi kendine dahil olan bir ortamdır. vcpkg herhangi bir ortam değişkenine eklenmez ve Windows kayıt defteri veya Visual Studio 'ya bağımlılığı yoktur.

## <a name="sources-not-binaries"></a>İkili dosyalar değil, kaynaklar

Windows kataloğundaki kitaplıklar için vcpkg, ikili dosyalar<sup>1</sup>yerine kaynakları indirir. Bu kaynakları, bulduğu Visual Studio 'nun en son sürümünü kullanarak derler. C++ ' da, hem uygulama kodunuzun hem de kullandığınız kitaplıkların aynı derleyici ve derleyici sürümü tarafından derlenmesi önemlidir. Vcpkg kullanarak, eşleşmeyen ikili dosyalar ve neden olabilecek sorunlar için potansiyelini ortadan kaldırır veya en azından büyük ölçüde azaltabilirsiniz. Bir derleyicinin belirli bir sürümünde standartlaştırılmış olan ekiplerde bir takım üyesi, kaynakları indirmek ve bir ikili dosya derlemek için vcpkg kullanabilir. Ardından, diğer takım üyeleri için ikili dosyaları ve üst bilgileri bağlamak üzere export komutunu kullanabilirler. Daha fazla bilgi için bkz. [derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma](#export_binaries_per_project) .

Ayrıca, bağlantı noktaları koleksiyonunda özel kitaplıkları olan bir vcpkg kopyası da oluşturabilirsiniz. Önceden oluşturulmuş ikili dosyalarınızı ve üst bilgilerinizi indiren bir bağlantı noktası ekleyin. Ardından, bu dosyaları yalnızca tercih edilen konuma kopyalayan bir portfile. CMake dosyası yazın.

<sup>1</sup> *Note: kaynaklar bazı özel kitaplıklar için kullanılamaz. Bu durumlarda, vcpkg, uyumlu önceden oluşturulmuş ikilileri indirir.*

## <a name="installation"></a>Yükleme

GitHub 'dan vcpkg deposunu kopyalayın: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg). İstediğiniz herhangi bir klasör konumuna indirebilirsiniz.

Önyükleyici kök klasörde çalıştırın:

- **bootstrap-vcpkg. bat** (Windows)
- **./Bootstrap-vcpkg.sh** (Linux, MacOS)

## <a name="search-the-list-of-available-libraries"></a>Kullanılabilir Kitaplıklar listesinde arama yapın

Hangi paketlerin kullanılabilir olduğunu görmek için, komut isteminde şunu yazın: **vcpkg arama**

Bu komut, vcpkg/Ports alt klasörlerindeki denetim dosyalarını numaralandırır. Şöyle bir liste görürsünüz:

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. \<https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

Bir modele filtre uygulayabilirsiniz; Örneğin, **vcpkg arama ta**:

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>Yerel makinenize kitaplık yükler

**Vcpkg aramasını**kullanarak bir kitaplığın adını aldıktan sonra, kitaplığı indirmek ve derlemek için **vcpkg yüklemesini** kullanırsınız. vcpkg, bağlantı noktaları dizininde kitaplığın portfile dosyasını kullanır. Hiçbir Üçlü izin belirtilmemişse, vcpkg hedef platform için varsayılan Üçlü değer için yüklenir ve derler: x86-Windows, x64-Linux. CMake veya x64-OSX. CMake.

Linux kitaplıkları için vcpkg, yerel makinede GCC 'nin yüklü olmasına bağlıdır. MacOS 'ta vcpkg, Clang kullanır.

Portfile bağımlılıkları belirttiğinde, vcpkg bunları indirir ve yükler. İndirmeden sonra, vcpkg kitaplığı, kitaplığın kullandığı yapı sistemini kullanarak oluşturur. CMake ve (Windows üzerinde) MSBuild projeleri tercih edilir, ancak diğer tüm derleme sistemleri ile birlikte desteklenir. Vcpkg, belirtilen yapı sistemini yerel makinede bulamazsa, indirir ve yükler.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

CMAKE projeleri için, kitaplıkları ile `find_package()`kullanılabilir hale getirmek için CMAKE_TOOLCHAIN_FILE kullanın. Örneğin:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake (Linux/MacOS)
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake (Windows)
```

## <a name="list-the-libraries-already-installed"></a>Zaten yüklü olan kitaplıkları listeleyin

Bazı kitaplıkları yükledikten sonra **vcpkg listesini** kullanarak neleri görmenizi sağlayabilirsiniz:

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="integrate-with-visual-studio-windows"></a>Visual Studio ile tümleştirme (Windows)

### <a name="per-user"></a>Kullanıcı başına

Visual Studio 'Yu, tüm vcpkg üst bilgi dosyalarını ve ikili dosyaları Kullanıcı başına temelinde bulacak şekilde yapılandırmak için **vcpkg tümleştirin Install** komutunu çalıştırın. VC + + Dizin yollarının el ile düzenlenmesine gerek yoktur. Birden çok klonunuz varsa, bu komutu çalıştırdığınız kopya yeni varsayılan konum olur.

Artık, klasörü/üstbilgiyi yazarak ve otomatik tamamlama size yardımcı olacak şekilde üstbilgileri #include. Kitaplıklar 'e bağlamak veya proje başvuruları eklemek için başka bir adım gerekmez. Aşağıdaki çizimde, Visual Studio 'Nun Azure-Storage-cpp üst bilgilerini nasıl bulduğu gösterilmektedir. vcpkg, üst bilgilerini hedef platforma göre bölümlenmiş **/yüklü** alt klasöre koyar. Aşağıdaki diyagramda, kitaplık için **/was** alt klasöründeki ekleme dosyalarının listesi gösterilmektedir:

![vcpkg ve IntelliSense](media/vcpkg-intellisense.png "vcpkg ve IntelliSense")

### <a name="per-project"></a>Proje başına

Bir kitaplığın, etkin vcpkg örneğindeki sürümden farklı olan belirli bir sürümünü kullanmanız gerekiyorsa, şu adımları izleyin:

1. Vcpkg 'nin yeni bir kopyasını oluşturun
1. Kitaplığın bağlantı noktası dosyasını, ihtiyacınız olan sürümü alacak şekilde değiştirin
1. **Vcpkg yüklemesi \<kitaplığı>** çalıştırın.
1. Her proje için bu kitaplığa başvuran bir NuGet paketi oluşturmak için **vcpkg tümleştir projesi** kullanın.

## <a name="integrate-with-visual-studio-code-linuxmacos"></a>Visual Studio Code ile tümleştirin (Linux/MacOS)

Linux/MacOS üzerinde Visual Studio Code yapılandırmak için **vcpkg tümleştirin Install** 'ı çalıştırın. Bu komut vcpkg kayıt konumunu ayarlar ve kaynak dosyalarında IntelliSense 'i sunar.

## <a name="target-linux-from-windows-via-wsl"></a>WSL aracılığıyla Windows 'dan Linux 'u hedefleyin

Linux için Windows alt sistemini veya WSL 'yi kullanarak bir Windows makinesinde Linux ikilileri oluşturabilirsiniz. Windows 10 ' da [WSL 'Yi ayarlama](/windows/wsl/install-win10)ve [Linux için Visual Studio uzantısı](https://blogs.msdn.microsoft.com/vcblog/2017/02/08/targeting-windows-subsystem-for-linux-from-visual-studio/)ile yapılandırma yönergelerini izleyin. Windows ve Linux için tüm yerleşik kitaplıklarınızı aynı klasöre yerleştirmekle sorunsuz. Bunlar hem Windows hem de WSL 'den erişilebilir.

## <a name="export-compiled-binaries-and-headers"></a><a name="export_binaries_per_project"></a>Derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma

Bir ekibin ortak kitaplıklarını indirmesi ve derlemesi için herkese açık hale getirmek verimsiz olur. Tek bir takım üyesi, ikili dosyalar ve üst bilgiler veya bir NuGet paketi için ortak bir ZIP dosyası oluşturmak üzere **vcpkg Export** komutunu kullanabilir. Daha sonra, diğer ekip üyeleriyle kolayca paylaşabilirsiniz.

## <a name="updateupgrade-installed-libraries"></a>Yüklü kitaplıkları güncelleştirme/yükseltme

Genel Katalog, kitaplıkların en son sürümleriyle güncel tutulur. Yerel kitaplıklarınızdan hangilerinin güncel kalmadığını öğrenmek için **vcpkg güncelleştirmesi**kullanın. Bağlantı noktası koleksiyonunuzu genel kataloğun en son sürümüne güncelleştirmeye hazırsanız, **vcpkg Upgrade** komutunu çalıştırın. Bu, güncel olmayan yüklü kitaplıklarınızın tümünü veya tümünü otomatik olarak indirir ve yeniden oluşturur.

Varsayılan olarak, **Upgrade** komutu yalnızca güncel olmayan kitaplıkları listeler; Onları yükseltmez. Kitaplıkları gerçekten yükseltmek için **--kuru-Çalıştır** seçeneğini kullanın.

```cmd
  vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>Yükseltme seçenekleri

- **--kuru çalıştırma**  Yükseltmeyi gerçekleştirin; belirtilmediğinde, komut yalnızca güncel olmayan paketleri listeler.
- **--sakla**  Başarısız olsa bile paketleri yüklemeye devam edin.
- **--Üçlü \<t>**  Nitelenmemiş paketler için varsayılan Üçlü değer ayarla ' yı ayarlayın.
- **--vcpkg-kök \<yolu>**  Geçerli dizin veya araç dizini yerine kullanılacak vcpkg dizinini belirtin.

### <a name="upgrade-example"></a>Yükseltme örneği

Aşağıdaki örnek, yalnızca belirtilen kitaplıkların nasıl yükseltileceğini gösterir. vcpkg, gerektiğinde otomatik olarak bağımlılıkları çeker.

```cmd
c:\users\satyan\vcpkg> vcpkg upgrade tiny-dnn:x86-windows zlib
The following packages are up-to-date:
   tiny-dnn:x86-windows

The following packages will be rebuilt:
    * libpng[core]:x86-windows
    * tiff[core]:x86-windows
      zlib[core]:x86-windows
Additional packages (*) will be modified to complete this operation.
If you are sure you want to rebuild the above packages, run this command with the --no-dry-run option.
```

## <a name="contribute-new-libraries"></a>Yeni kitaplıklara katkıda bulunma

Özel bağlantı noktaları koleksiyonunuzda istediğiniz kitaplıkları dahil edebilirsiniz. Ortak kataloğa yönelik yeni bir kitaplık önermek için [GitHub vcpkg sorun sayfasında](https://github.com/Microsoft/vcpkg/issues)bir sorun açın.

## <a name="remove-a-library"></a>Kitaplığı kaldırma

Yüklü bir kitaplığı kaldırmak için **vcpkg Remove** yazın. Başka herhangi bir kitaplık buna bağımlıysa, tüm aşağı akış kitaplıklarının kaldırılmasına neden olan **--Recurse**komutunu kullanarak komutu yeniden çalıştırmanız istenir.

## <a name="customize-vcpkg"></a>Vcpkg 'yi özelleştirme

Vcpkg klonınızı dilediğiniz şekilde değiştirebilirsiniz. Hatta birden çok vcpkg klonları oluşturabilir, ardından her birindeki portfiles 'ı değiştirebilirsiniz. Bu, belirli kitaplık sürümlerini almanın veya belirli komut satırı parametrelerinin belirtilmesi için basit bir yoldur. Örneğin, bir kuruluşta, tek tek geliştiricilerin grupları, gruplarına özgü bir bağımlılıklar kümesine sahip yazılımlar üzerinde çalışabilir. Bu çözüm, her takım için vcpkg 'nin bir kopyasını ayarlamaya yöneliktir. Ardından, kitaplık sürümlerini indirmek ve her ekibin ihtiyaç duyacağı derleme anahtarlarını ayarlamak için klonları değiştirin.

## <a name="uninstall-vcpkg"></a>Vcpkg 'yi kaldır

Vcpkg dizinini silmeniz yeterlidir. Bu dizinin silinmesi vcpkg dağıtımını kaldırır ve vcpkg 'nin yüklü olduğu tüm kitaplıkları kaldırır.

## <a name="send-feedback-about-vcpkg"></a>Vcpkg hakkında geri bildirim gönderin

Hata raporları ve özellikler için öneriler de dahil olmak üzere vcpkg hakkında Microsoft 'a geri bildirim göndermek için **vcpkg iletişim--anket** komutunu kullanın.

## <a name="the-vcpkg-folder-hierarchy"></a>Vcpkg klasör hiyerarşisi

Tüm vcpkg işlevleri ve verileri, "örnek" olarak adlandırılan tek bir Dizin hiyerarşisinde kendiliğinden bulunur. Kayıt defteri ayarları veya ortam değişkeni yok. Bir makine üzerinde herhangi bir sayıda vcpkg örneğine sahip olabilirsiniz ve birbirini engellemez.

Vcpkg örneğinin içeriği şunlardır:

- buildtrees--her kitaplığın oluşturulduğu kaynak alt klasörlerini içerir
- docs--belgeler ve örnekler
- İndirmeler--indirilen araçların veya kaynakların önbelleğe alınmış kopyaları. vcpkg, Install komutunu çalıştırdığınızda önce burada arama yapar.
- yüklü--yüklü olan her kitaplığın üst bilgilerini ve ikili dosyalarını Içerir. Visual Studio ile tümleştirdiğinizde, temelde bu klasörü arama yollarına eklemesini söylemiş olursunuz.
- paketler--yüklemeler arasında hazırlama için Iç klasör.
- bağlantı noktaları--katalogdaki her kitaplığı, sürümünü ve nereden indirileceği dosyaları. Gerekirse, kendi bağlantı noktalarınızı ekleyebilirsiniz.
- betikler--vcpkg tarafından kullanılan betikler (CMake, PowerShell).
- toolsrc--vcpkg ve ilgili bileşenler için C++ kaynak kodu
- Üçlü izin--desteklenen her bir hedef platformun (örneğin, x86-Windows veya x64-UWP) ayarlarını Içerir.

## <a name="command-line-reference"></a>Komut satırı başvurusu

|Komut|Açıklama|
|---------|---------|
|**vcpkg Search \[Pat]**|Yüklemek için kullanılabilir paketleri ara|
|**vcpkg pkg \<> yüklemesi...**|Paket yükler|
|**vcpkg pkg \<> kaldır...**|Bir paketi kaldırma|
|**vcpkg kaldır--güncel değil**|Tüm güncel paketleri kaldır|
|**vcpkg listesi**|Yüklü paketleri Listele|
|**vcpkg güncelleştirmesi**|Güncelleştirme için paketlerin listesini görüntüle|
|**vcpkg yükseltmesi**|Tüm eski paketleri yeniden derle|
|**vcpkg karma \<dosyası> \[alg]**|Belirli bir algoritmayla bir dosyayı karma, varsayılan SHA512 olur|
|**vcpkg tümleştir yüklemesi**|Yüklü paketleri Kullanıcı genelinde kullanılabilir hale getirin. İlk kullanımda yönetici ayrıcalıkları gerektirir|
|**vcpkg tümleştir kaldır**|Kullanıcı genelinde tümleştirmeyi kaldırma|
|**vcpkg tümleştir projesi**|Tek tek VS projesi kullanımı için başvuran bir NuGet paketi oluşturma|
|**vcpkg dışarı \<aktarma pkg>... \[opt]...**|Paketi dışarı aktarma|
|**vcpkg pkg \<>düzenleme**|Düzenleme için bir bağlantı noktası açın (% EDITOR%, varsayılan ' Code ' kullanır)|
|**vcpkg pkg \<> \<> \[URL 'si oluştur**|Yeni bir paket oluştur|
|**vcpkg önbelleği**|Önbelleğe alınmış derlenmiş paketleri Listele|
|**vcpkg sürümü**|Sürüm bilgilerini görüntüle|
|**vcpkg ilgili kişisi--anket**|Geri bildirim göndermek için kişi bilgilerini görüntüleyin.|

### <a name="options"></a>Seçenekler

|Seçenek|Açıklama|
|---------|---------|
|**--Üçlü \<t>**|Hedef mimari, Üçlü mimari belirtin. (varsayılan: `%VCPKG_DEFAULT_TRIPLET%`, Ayrıca bkz. **vcpkg yardım Üçlü izin**)|
|**--vcpkg-kök \<yolu>**|Vcpkg kök dizinini belirtin (varsayılan: `%VCPKG_ROOT%`)|
