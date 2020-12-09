---
title: 'vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi'
description: vcpkg, Windows, macOS ve Linux 'ta açık kaynaklı C++ kitaplıklarının alımı ve yüklemesini büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir.
ms.date: 07/06/2020
ms.technology: cpp-ide
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.openlocfilehash: ec908824c19099ad6eaa46a4d85c0187ef12b3fd
ms.sourcegitcommit: 102bd6f7a878d85c8ceab8f28d0359f562850ea0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/08/2020
ms.locfileid: "96862561"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi

vcpkg, C++ için bir komut satırı paket yöneticisidir. Windows, Linux ve macOS 'ta üçüncü taraf kitaplıkların Alım ve yükleme işlemlerini büyük ölçüde basitleştirir. Projeniz üçüncü taraf kitaplıklar kullanıyorsa, bunları yüklemek için vcpkg kullanmanızı öneririz. vcpkg hem açık kaynaklı hem de özel kitaplıkları destekler. Vcpkg Windows kataloğundaki tüm kitaplıklar, Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 uyumluluğu için test edilmiştir. Windows ve Linux/macOS katalogları arasında vcpkg artık 1900 ' den fazla kitaplığı desteklemektedir. C++ topluluğu, her iki katalogda de sürekli olarak daha fazla kitaplık ekliyor.

## <a name="simple-yet-flexible"></a>Basit ancak esnek

Tek bir komutla kaynakları indirebilir ve bir kitaplık oluşturabilirsiniz. vcpkg, GitHub 'da bulunan açık kaynaklı bir projem. Özel vcpkg klonlarınızı dilediğiniz şekilde özelleştirmek mümkündür. Örneğin, genel katalogda bulunanlara göre farklı kitaplıklar ya da kitaplıkların farklı sürümlerini belirtin. Tek bir makineye birden fazla vcpkg klonda sahip olabilirsiniz. Her biri, tercih ettiğiniz derleme anahtarlarınız ile özel bir kitaplık koleksiyonu oluşturmak üzere ayarlanabilir. Her kopya, kendi kendi hiyerarşisinde çalışan vcpkg.exe kendi kopyasıyla kendi kendine dahil olan bir ortamdır. vcpkg herhangi bir ortam değişkenine eklenmez ve Windows kayıt defteri veya Visual Studio 'ya bağımlılığı yoktur.

## <a name="sources-not-binaries"></a>İkili dosyalar değil, kaynaklar

Windows kataloğundaki kitaplıklar için vcpkg, ikili dosyalar<sup>1</sup>yerine kaynakları indirir. Bu kaynakları, bulduğu Visual Studio 'nun en son sürümünü kullanarak derler. C++ ' da, hem uygulama kodunuzun hem de kullandığınız kitaplıkların aynı derleyici ve derleyici sürümü tarafından derlenmesi önemlidir. Vcpkg kullanarak, eşleşmeyen ikili dosyalar ve neden olabilecek sorunlar için potansiyelini ortadan kaldırır veya en azından büyük ölçüde azaltabilirsiniz. Bir derleyicinin belirli bir sürümünde standartlaştırılmış olan ekiplerde bir takım üyesi, kaynakları indirmek ve bir ikili dosya derlemek için vcpkg kullanabilir. Ardından, diğer takım üyeleri için ikili dosyaları ve üst bilgileri bağlamak üzere export komutunu kullanabilirler. Daha fazla bilgi için bkz. [derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma](#export_binaries_per_project) .

Ayrıca, bağlantı noktaları koleksiyonunda özel kitaplıkları olan bir vcpkg kopyası da oluşturabilirsiniz. Önceden oluşturulmuş ikili dosyalarınızı ve üst bilgilerinizi indiren bir bağlantı noktası ekleyin. Ardından, bu dosyaları yalnızca tercih edilen konuma kopyalayan bir *portfile. CMake* dosyası yazın.

<sup>1</sup> *Note: kaynaklar bazı özel kitaplıklar için kullanılamaz. Bu durumlarda, vcpkg, uyumlu önceden oluşturulmuş ikilileri indirir.*

## <a name="installation"></a>Yükleme

GitHub 'dan vcpkg deposunu kopyalayın: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) . İstediğiniz herhangi bir klasör konumuna indirebilirsiniz. Bu konum vcpkg *köküdür*. İndirme işlemi tamamlandıktan sonra komut kabuğunuzun bu dizine geçin.

Vcpkg kök dizininde vcpkg Önyükleyicisi çalıştırın:

- **`bootstrap-vcpkg.bat`** Pencerelerin
- **`./bootstrap-vcpkg.sh`** (Linux, macOS)

Linux veya macOS 'ta, aşağıdaki örneklerde, vcpkg komutlarına önek uygulamanız gerekebilir **`./`** . Bu komutları vcpkg kök dizininden çalıştırmayı unutmayın.

## <a name="search-the-list-of-available-libraries"></a>Kullanılabilir Kitaplıklar listesinde arama yapın

Hangi paketlerin kullanılabilir olduğunu görmek için **`vcpkg search`** komut istemine yazın.

Bu komut, *vcpkg/Ports* alt klasörlerindeki denetim dosyalarını numaralandırır. Şöyle bir liste görürsünüz:

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

Bir modele filtre uygulayabilirsiniz, örneğin **`vcpkg search ta`** :

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>Yerel makinenize kitaplık yükler

Kullanarak bir kitaplığın adını aldıktan sonra **`vcpkg search`** , **`vcpkg install`** kitaplığı indirmek ve derlemek için kullanın. vcpkg, *bağlantı noktaları* dizininde kitaplığın portfile dosyasını kullanır. Bir üçlü değer belirtilmemişse, vcpkg, hedef platform için varsayılan Üçlü değer için yüklenir ve derlenir: x86-Windows, x64-Linux. CMake veya x64-OSX. CMake.

Linux kitaplıkları için vcpkg, yerel makinede GCC 'nin yüklü olmasına bağlıdır. MacOS 'ta vcpkg, Clang kullanır.

Portfile bağımlılıkları belirttiğinde, vcpkg bunları indirir ve yükler. İndirmeden sonra, vcpkg kitaplığı, kitaplığın kullandığı yapı sistemini kullanarak oluşturur. CMake ve (Windows üzerinde) MSBuild projeleri tercih edilir, ancak başka bir derleme sistemiyle birlikte desteklenir. Vcpkg, belirtilen yapı sistemini yerel makinede bulamazsa, indirir ve yükler.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

CMake projeleri için, `CMAKE_TOOLCHAIN_FILE` kitaplıklarını ile kullanılabilir hale getirmek için kullanın `find_package()` . Örneğin, Linux veya macOS 'ta:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake
```

Windows'da:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake
```

Bazı kitaplıklar yüklenebilir seçenekleri içerir. Örneğin, kıvrımlı kitaplığı aradığınızda, köşeli ayraçlar içinde desteklenen seçeneklerin bir listesini de görürsünüz:

```cmd
> vcpkg search curl
curl                 7.68.0-3         A library for transferring data with URLs
curl[tool]                            Builds curl executable
curl[non-http]                        Enables protocols beyond HTTP/HTTPS/HTTP2
curl[http2]                           HTTP2 support
curl[ssl]                             Default SSL backend
curl[ssh]                             SSH support via libssh2
curl[openssl]                         SSL support (OpenSSL)
curl[winssl]                          SSL support (Secure Channel / "WinSSL")
curl[mbedtls]                         SSL support (mbedTLS)
curl[sectransp]                       SSL support (sectransp)
curl[c-ares]                          c-ares support
curl[sspi]                            SSPI support
curl[brotli]                          brotli support (brotli)
curlpp               2018-06-15-3     C++ wrapper around libcURL
```

Bu durumda, köşeli ayraçlar **`[`** ve **`]`** meta karakterler değil değişmez değer.

Komut satırına yüklemek için belirli bir seçenek belirleyebilirsiniz. Örneğin, Windows için varsayılan SSL arka ucunu kullanarak, kıvrımlı kitaplıklar yüklemek için **`vcpkg install curl[ssl]:x86-windows`** komutunu kullanın. Bu komut, gerekirse Çekirdek Kitaplığı da dahil olmak üzere tüm gerekli önkoşulları yüklüyor:

```cmd
> vcpkg list
curl:x86-windows            7.68.0-3   A library for transferring data with URLs
curl[non-http]:x86-windows             Enables protocols beyond HTTP/HTTPS/HTTP2
curl[ssl]:x86-windows                  Default SSL backend
curl[sspi]:x86-windows                 SSPI support
curl[winssl]:x86-windows               SSL support (Secure Channel / "WinSSL")
zlib:x86-windows            1.2.11-6   A compression library
```

## <a name="list-the-libraries-already-installed"></a>Zaten yüklü olan kitaplıkları listeleyin

Bazı kitaplıkları yükledikten sonra, şunları **`vcpkg list`** görmek için kullanabilirsiniz:

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

**`vcpkg integrate install`** Visual Studio 'yu, tüm vcpkg üst bilgi dosyalarını ve ikili dosyaları Kullanıcı başına temelinde bulacak şekilde yapılandırmak için komutunu çalıştırın. VC + + Dizin yollarının el ile düzenlenmesine gerek yoktur. Vcpkg 'nin birden çok klonunuz varsa, bu komutu çalıştırdığınız kopya yeni varsayılan konum olur.

Artık, klasörü/üstbilgiyi yazarak ve otomatik tamamlama size yardımcı olacak şekilde üstbilgileri #include. Kitaplıklar 'e bağlamak veya proje başvuruları eklemek için başka bir adım gerekmez. Aşağıdaki çizimde, Visual Studio 'Nun Azure-Storage-cpp üst bilgilerini nasıl bulduğu gösterilmektedir. vcpkg, üst bilgilerini hedef platforma göre bölümlenmiş */yüklü* alt klasöre koyar. Aşağıdaki diyagramda, kitaplık için */was* alt klasöründeki ekleme dosyalarının listesi gösterilmektedir:

![vcpkg ve IntelliSense](media/vcpkg-intellisense.png "vcpkg ve IntelliSense")

### <a name="per-project"></a>Proje başına

Bir kitaplığın, etkin vcpkg örneğindeki sürümden farklı olan belirli bir sürümünü kullanmanız gerekiyorsa, şu adımları izleyin:

1. Vcpkg 'nin yeni bir kopyasını oluşturun
1. Kitaplığın bağlantı noktası dosyasını, ihtiyacınız olan sürümü alacak şekilde değiştirin
1. Öğesini çalıştırın **`vcpkg install <library>`** .
1. **`vcpkg integrate project`** Projeye göre bu kitaplığa başvuran bir NuGet paketi oluşturmak için kullanın.

## <a name="integrate-with-visual-studio-code-linuxmacos"></a>Visual Studio Code ile tümleştirin (Linux/macOS)

**`vcpkg integrate install`** Linux/macOS üzerinde Visual Studio Code yapılandırmak için çalıştırın. Bu komut vcpkg kayıt konumunu ayarlar ve kaynak dosyalarında IntelliSense 'i sunar.

## <a name="target-linux-from-windows-via-wsl"></a>WSL aracılığıyla Windows 'dan Linux 'u hedefleyin

Linux için Windows alt sistemini veya WSL 'yi kullanarak bir Windows makinesinde Linux ikilileri oluşturabilirsiniz. [Windows 10 ' da WSL 'Yi ayarlamak](/windows/wsl/install-win10)için yönergeleri izleyin. Ardından, [Linux Için Visual Studio uzantısıyla](https://devblogs.microsoft.com/cppblog/targeting-windows-subsystem-for-linux-from-visual-studio/)yapılandırın. Windows ve Linux için tüm yerleşik kitaplıklarınızı aynı klasöre yerleştirmekle sorunsuz. Bunlar hem Windows hem de WSL 'den erişilebilir.

## <a name="export-compiled-binaries-and-headers"></a><a name="export_binaries_per_project"></a> Derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma

Bir ekibin ortak kitaplıklarını indirmesi ve derlemesi için herkese açık hale getirmek verimsiz olur. Tek bir takım üyesi, **`vcpkg export`** ikili dosyaları ve üstbilgileri veya bir NuGet paketini ortak bir ZIP dosyası oluşturmak için komutunu kullanabilir. Daha sonra, diğer ekip üyeleriyle kolayca paylaşabilirsiniz.

## <a name="updateupgrade-installed-libraries"></a>Yüklü kitaplıkları güncelleştirme/yükseltme

Genel Katalog, kitaplıkların en son sürümleriyle güncel tutulur. Yerel kitaplıklarınızdan hangilerinin güncel kalmadığını öğrenmek için kullanın **`vcpkg update`** . Bağlantı noktası koleksiyonunuzu ortak kataloğun en son sürümüne güncelleştirmeye hazırsanız **`vcpkg upgrade`** komutunu çalıştırın. Bu, güncel olmayan yüklü kitaplıklarınızın tümünü veya tümünü otomatik olarak indirir ve yeniden oluşturur.

Varsayılan olarak, **`vcpkg upgrade`** komut yalnızca güncel olmayan kitaplıkları listeler; bunları yükseltmez. Kitaplıkları gerçekten yükseltmek için **`--no-dry-run`** seçeneğini kullanın.

```cmd
> vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>Yükseltme seçenekleri

- **`--no-dry-run`**  Yükseltmeyi gerçekleştirin; belirtilmediğinde, komut yalnızca güncel olmayan paketleri listeler.
- **`--keep-going`**  Başarısız olsa bile paketleri yüklemeye devam edin.
- **`--triplet <t>`**  Nitelenmemiş paketler için varsayılan Üçlü değer ayarla ' yı ayarlayın.
- **`--vcpkg-root <path>`**  Geçerli dizin veya araç dizini yerine kullanılacak vcpkg dizinini belirtin.

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

**`vcpkg remove`** Yüklü bir kitaplığı kaldırmak için yazın. Başka herhangi bir kitaplık buna bağımlıysa, **`--recurse`** tüm aşağı akış kitaplıklarının kaldırılmasına neden olan komutunu ile yeniden çalıştırmanız istenir.

## <a name="customize-vcpkg"></a>Vcpkg 'yi özelleştirme

Vcpkg klonınızı dilediğiniz şekilde değiştirebilirsiniz. Hatta birden çok vcpkg klonları oluşturabilir, ardından her birindeki portfiles 'ı değiştirebilirsiniz. Bu, belirli kitaplık sürümlerini almanın veya belirli komut satırı parametrelerinin belirtilmesi için basit bir yoldur. Örneğin, bir kuruluştaki bireysel geliştiricilerin grupları, gruplarına özgü bağımlılıklara sahip yazılımlar üzerinde çalışabilir. Bu çözüm, her takım için vcpkg 'nin bir kopyasını ayarlamaya yöneliktir. Ardından, kitaplık sürümlerini indirmek ve her ekibin ihtiyaç duyacağı derleme anahtarlarını ayarlamak için klonları değiştirin.

## <a name="update-vcpkg"></a>Vcpkg 'yi Güncelleştir

Vcpkg Paket Yöneticisi GitHub 'da düzenli olarak güncelleştirilir. Vcpkg klonınızı en son sürüme güncelleştirmek için vcpkg kök dizininden öğesini çalıştırın **`git pull`** . Bu komut, vcpkg kopyanızı GitHub 'daki sürümle eşitler. İndirme tamamlandıktan sonra, önyükleyiciyi yeniden çalıştırın. Önyükleyici vcpkg programını yeniden oluşturur, ancak yüklü kitaplıklarınızı yerinde bırakır.

## <a name="uninstall-vcpkg"></a>Vcpkg 'yi kaldır

Vcpkg 'yi kaldırmak için vcpkg dizinini silmeniz yeterlidir. Bu dizinin silinmesi vcpkg dağıtımını kaldırır ve vcpkg 'nin yüklü olduğu tüm kitaplıkları kaldırır.

Ancak, yürütülürse **`vcpkg integrate install`** **`vcpkg integrate remove`** , klasör kaldırılmadan önce tümleştirmenin temizlendiğinden emin olmak için yürütmelisiniz.

## <a name="send-feedback-about-vcpkg"></a>Vcpkg hakkında geri bildirim gönderin

**`vcpkg contact --survey`** Hata raporları ve özellikler için öneriler de dahil olmak üzere Microsoft 'a vcpkg hakkında geri bildirim göndermek için komutunu kullanın.

## <a name="the-vcpkg-folder-hierarchy"></a>Vcpkg klasör hiyerarşisi

Tüm vcpkg işlevleri ve verileri, "örnek" olarak adlandırılan tek bir Dizin hiyerarşisinde kendiliğinden bulunur. Kayıt defteri ayarları veya ortam değişkeni yok. Bir makine üzerinde herhangi bir sayıda vcpkg örneğine sahip olabilirsiniz ve birbirini engellemez.

Vcpkg örneğinin içeriği şunlardır:

- buildtrees-her kitaplığın oluşturulduğu kaynak alt klasörlerini içerir
- docs-belgeler ve örnekler
- indirmelere indirilen araçların veya kaynakların önbelleğe alınmış kopyaları. vcpkg, Install komutunu çalıştırdığınızda önce burada arama yapar.
- yüklü-yüklü her kitaplık için üst bilgileri ve ikili dosyaları Içerir. Visual Studio ile tümleştirdiğinizde, temelde bu klasörü arama yollarına eklemesini söylemiş olursunuz.
- paketler-yüklemeler arasında hazırlama için Iç klasör.
- bağlantı noktaları-katalogdaki her kitaplığı, sürümünü ve nereden indirileceği dosyaları. Gerekirse, kendi bağlantı noktalarınızı ekleyebilirsiniz.
- komut dosyaları (CMake, PowerShell) vcpkg tarafından kullanılır.
- toolsrc-vcpkg ve ilgili bileşenler için C++ kaynak kodu
- Üçlü izin-her desteklenen hedef platformun (örneğin, x86-Windows veya x64-UWP) ayarlarını Içerir.

## <a name="command-line-reference"></a>Komut satırı başvurusu

|Komut|Açıklama|
|---------|---------|
|**`vcpkg search [pat]`**|Yüklemek için kullanılabilir paketleri ara|
|**`vcpkg install <pkg>...`**|Paketi yükleme|
|**`vcpkg remove <pkg>...`**|Bir paketi kaldırma|
|**`vcpkg remove --outdated`**|Tüm güncel paketleri kaldır|
|**`vcpkg list`**|Yüklü paketleri Listele|
|**`vcpkg update`**|Güncelleştirme için paketlerin listesini görüntüle|
|**`vcpkg upgrade`**|Tüm eski paketleri yeniden derle|
|**`vcpkg hash <file> [alg]`**|Belirli bir algoritmayla bir dosyayı karma, varsayılan SHA512 olur|
|**`vcpkg integrate install`**|Yüklü paketleri Kullanıcı genelinde kullanılabilir hale getirin. İlk kullanımda yönetici ayrıcalıkları gerektirir|
|**`vcpkg integrate remove`**|Kullanıcı genelinde tümleştirmeyi kaldırma|
|**`vcpkg integrate project`**|Tek tek VS projesi kullanımı için başvuran bir NuGet paketi oluşturma|
|**`vcpkg export <pkg>... [opt]...`**|Paketi dışarı aktarma|
|**`vcpkg edit <pkg>`**|Düzenleme için bir bağlantı noktası açın (% EDITOR%, varsayılan ' Code ' kullanır)|
|**`vcpkg create <pkg> <url> [archivename]`**|Yeni bir paket oluştur|
|**`vcpkg cache`**|Önbelleğe alınmış derlenmiş paketleri Listele|
|**`vcpkg version`**|Sürüm bilgilerini görüntüle|
|**`vcpkg contact --survey`**|Geri bildirim göndermek için kişi bilgilerini görüntüleyin.|

### <a name="options"></a>Seçenekler

|Seçenek|Açıklama|
|---------|---------|
|**`--triplet <t>`**|Hedef mimari, Üçlü mimari belirtin. (varsayılan: `%VCPKG_DEFAULT_TRIPLET%` , Ayrıca bkz. **`vcpkg help triplet`** )|
|**`--vcpkg-root <path>`**|Vcpkg kök dizinini belirtin (varsayılan: `%VCPKG_ROOT%` )|
