---
title: 'vcpkg: Windows, Linux ve MacOS için bir C++ paket yöneticisi'
description: vcpkg, Windows, MacOS ve Linux'ta açık kaynak C++ kitaplıklarının edinimi ve yüklenmesini büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir.
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
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Windows, Linux ve MacOS için bir C++ paket yöneticisi

vcpkg, C++'ın komut satırı paket yöneticisidir. Windows, Linux ve MacOS'ta üçüncü taraf kitaplıklarının edinimi ve yüklenmesini büyük ölçüde kolaylaştırır. Projenizde üçüncü taraf kitaplıklar kullanılıyorsa, bunları yüklemek için vcpkg kullanmanızı öneririz. vcpkg hem açık kaynak hem de özel kitaplıkları destekler. vcpkg Windows kataloğundaki tüm kütüphaneler Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 ile uyumluluk açısından test edilmiştir. VCPKG, Windows ve Linux/MacOS katalogları arasında şu anda 1900'den fazla kitaplığı desteklemektedir. C++ topluluğu her iki kataloğu da sürücüden daha fazla kitaplık ekliyor.

## <a name="simple-yet-flexible"></a>Basit ama esnek

Tek bir komutla kaynakları karşıdan yükleyebilir ve kitaplık oluşturabilirsiniz. vcpkg kendisi github kullanılabilir bir açık kaynak projesidir. Özel vcpkg klonlarınızı istediğiniz şekilde özelleştirmek mümkündür. Örneğin, ortak katalogda bulunanlardan farklı kitaplıklar veya kitaplıkların farklı sürümlerini belirtin. Tek bir makinede birden fazla vcpkg klonu olabilir. Her biri, tercih ettiğiniz derleme anahtarlarıyla özel bir kitaplık koleksiyonu oluşturmak üzere ayarlanabilir. Her klon sadece kendi hiyerarşisi üzerinde çalışan vcpkg.exe kendi kopyası ile kendi kendine yeten bir ortamdır. vcpkg herhangi bir ortam değişkenine eklenmez ve Windows Kayıt Defteri veya Visual Studio'ya bağımlı değildir.

## <a name="sources-not-binaries"></a>Kaynaklar, ikili değil

Windows kataloğundaki kitaplıklar için, vcpkg<sup>ikili</sup>1 yerine kaynak indirir. Bu kaynakları Visual Studio'nun bulabileceği en son sürümünü kullanarak derler. C++'da, hem uygulama kodunuzu hem de kullandığınız kitaplıkların aynı derleyici ve derleyici sürümü tarafından derlenmiş olması önemlidir. Vcpkg kullanarak, uyumsuz ikililer ve neden olabilecek sorunlar için potansiyelortadan kaldırmak veya en azından büyük ölçüde azaltır. Derleyicinin belirli bir sürümünde standartlaştırılmış takımlarda, bir ekip üyesi kaynakları indirmek ve bir dizi ikili derlemek için vcpkg kullanabilir. Daha sonra diğer takım üyeleri için ikili ve üstbilgi fermuarları hızlandırmak için dışa aktarma komutunu kullanabilirsiniz. Daha fazla bilgi için aşağıdaki [derlenmiş ikili ve üstbilgilere](#export_binaries_per_project) export'a bakın.

Ayrıca, bağlantı noktaları koleksiyonunda özel kitaplıklar bulunan bir vcpkg klonu da oluşturabilirsiniz. Önceden oluşturulmuş ikililerinizi ve üstbilgilerinizi indiren bir bağlantı noktası ekleyin. Ardından, bu dosyaları tercih edilen konuma kopyalayan bir portfile.cmake dosyası yazın.

<sup>1</sup> *Not: kaynaklar bazı özel kitaplıklar için kullanılamaz. Bu gibi durumlarda, vcpkg uyumlu önceden oluşturulmuş ikili indirir.*

## <a name="installation"></a>Yükleme

GitHub vcpkg repo klonlamak: [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg). İstediğiniz klasör konumuna indirebilirsiniz.

Bootstrapper'ı kök klasöründe çalıştırın:

- **bootstrap-vcpkg.bat** (Windows)
- **./bootstrap-vcpkg.sh** (Linux, MacOS)

## <a name="search-the-list-of-available-libraries"></a>Kullanılabilir kitaplıkların listesini arama

Hangi paketlerin mevcut olduğunu görmek için komut istemi türünde: **vcpkg arama**

Bu komut, vcpkg/bağlantı noktaları alt klasörlerinde kontrol dosyalarını doğrular. Şöyle bir liste görürsünüz:

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

Bir desen filtreleyebilirsiniz, örneğin **vcpkg arama ta:**

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>Yerel makinenize kitaplık yükleme

**Vcpkg aramasını**kullanarak bir kütüphanenin adını aldıktan sonra, kitaplığı indirmek ve derlemek için **vcpkg install'ı** kullanırsınız. vcpkg, kitaplığın bağlantı noktaları dizininde portfilesini kullanır. Hiçbir üçüz belirtilmemişse, vcpkg yüklenir ve hedef platform için varsayılan üçlü için derlenir: x86-windows, x64-linux.cmake veya x64-osx.cmake.

Linux kitaplıkları için vcpkg, yerel makineye gcpkg yüklenmesine bağlıdır. MacOS'ta vcpkg Clang kullanır.

Portfile bağımlılıkları belirttiğinde, vcpkg indirir ve yükler. VCPKG, indirdikten sonra, kitaplığın kullandığı yapı sistemini kullanarak kitaplığı oluşturur. CMake ve (Windows' da) MSBuild projeleri tercih edilir, ancak MAKE, diğer yapı sistemiyle birlikte desteklenir. Vcpkg yerel makinede belirtilen yapı sistemini bulamazsa, karşıdan yükler ve yükler.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

CMAKE projeleri için, CMAKE_TOOLCHAIN_FILE'yi `find_package()`kullanarak kitaplıkları ' nın kullanılabilir olmasını sağlayabilir. Örneğin:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake (Linux/MacOS)
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake (Windows)
```

## <a name="list-the-libraries-already-installed"></a>Zaten yüklü olan kitaplıkları listele

Bazı kitaplıklar yükledikten sonra, sahip olduğunuz kitaplıkları görmek için **vcpkg listesini** kullanabilirsiniz:

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="integrate-with-visual-studio-windows"></a>Visual Studio (Windows) ile tümleştirme

### <a name="per-user"></a>Kullanıcı başına

Tüm vcpkg üstbilgi dosyalarını ve ikililerini kullanıcı başına bulmak için Visual Studio'yı yapılandırmak için **vcpkg tümleştirme yüklemesini** çalıştırın. VC++ Dizin yollarının manuel olarak düzenlenmesine gerek yoktur. Birden çok klon'unuzun varsa, bu komutu çalıştırdığınız klon yeni varsayılan konum olur.

Artık yalnızca klasörü/üstbilgiyi yazarak üstbilgi #include ve otomatik tamamlama size yardımcı olur. Libs'e bağlanmak veya proje başvuruları eklemek için ek adım gerekmez. Aşağıdaki resimde Visual Studio'nun azure-depolama-cpp üstbilgileri nasıl bulduğunu gösterilmektedir. vcpkg üstbilgilerini hedef platforma göre bölümlenmiş **/yüklü** alt klasöre yerleştirir. Aşağıdaki diyagram, kitaplık için **/was** alt klasöründe bulunan dosyaların listesini gösterir:

![vcpkg ve IntelliSense](media/vcpkg-intellisense.png "vcpkg ve IntelliSense")

### <a name="per-project"></a>Proje başına

Etkin vcpkg örneğindeki sürümden farklı bir kitaplığın belirli bir sürümünü kullanmanız gerekiyorsa, aşağıdaki adımları izleyin:

1. Vcpkg'nin yeni bir klonunu yapın
1. İhtiyacınız olan sürümü elde etmek için kitaplık için bağlantı noktası dosyasını değiştirme
1. Çalıştır **vcpkg \<yükleme kitaplığı>. **
1. Bu kitaplığı proje başına başvuran bir NuGet paketi oluşturmak için **vcpkg tümleştirme projesini** kullanın.

## <a name="integrate-with-visual-studio-code-linuxmacos"></a>Visual Studio Code (Linux/MacOS) ile tümleştirme

Linux/MacOS'ta Visual Studio Code yapılandırmak için **vcpkg tümleştirme yüklemesini** çalıştırın. Bu komut vcpkg listesinin yerini ayarlar ve kaynak dosyalarda IntelliSense'i etkinleştiri.

## <a name="target-linux-from-windows-via-wsl"></a>WSL üzerinden Windows'tan Hedef Linux

Linux için Windows Alt Sistemi'ni veya WSL'yi kullanarak Windows makinesinde Linux ikilileri oluşturabilirsiniz. [Windows 10'da WSL'yi kurmak](/windows/wsl/install-win10)için yönergeleri izleyin ve [Linux için Visual Studio uzantısı](https://blogs.msdn.microsoft.com/vcblog/2017/02/08/targeting-windows-subsystem-for-linux-from-visual-studio/)ile yapılandırın. Windows ve Linux için tüm yerleşik kitaplıklarınızı aynı klasöre koymanızda bir sakınca yok. Hem Windows hem de WSL'den erişilebilirler.

## <a name="export-compiled-binaries-and-headers"></a><a name="export_binaries_per_project"></a>Derlenen ikilileri ve üstbilgileri dışa aktarma

Ekipteki herkesin ortak kitaplıkları karşıdan yüklemesini ve oluşturmasını sağlamak verimsizdir. Tek bir ekip üyesi, ikili ve üstbilgiden oluşan ortak bir zip dosyası veya NuGet paketi oluşturmak için **vcpkg dışa aktarma** komutunu kullanabilir. Ardından, diğer ekip üyeleriyle paylaşmak kolaydır.

## <a name="updateupgrade-installed-libraries"></a>Yüklü kitaplıkları güncelleştirme/yükseltme

Genel katalog, kitaplıkların en son sürümleriyle güncel tutulur. Yerel kitaplıklarınızdan hangisinin güncel olmadığını belirlemek için **vcpkg güncelleştirmesini**kullanın. Bağlantı noktaları koleksiyonunuzu genel kataloğun en son sürümüne güncellemeye hazır **olduğunuzda, vcpkg yükseltme** komutunu çalıştırın. Güncel olmayan yüklü kitaplıklarınızın herhangi birini veya tümlerini otomatik olarak karşıdan yükler ve yeniden yükler.

Varsayılan olarak, **yükseltme** komutu yalnızca güncel olmayan kitaplıkları listeler; onları yükseltmez. Kitaplıkları gerçekten yükseltmek için **--kuru çalıştırma seçeneğini** kullanın.

```cmd
  vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>Yükseltme Seçenekleri

- **--kuru-çalıştırılması**  Yükseltmeyi gerçekleştirin; belirtilmediğinde, komut yalnızca güncel olmayan paketleri listeler.
- **--devam et**  Biri başarısız olsa bile paketleri yüklemeye devam edin.
- **--üçüz \<t>**  Niteliksiz paketler için varsayılan üçüz'u ayarlayın.
- **--vcpkg-kök \<yol>**  Geçerli dizin veya araç dizini yerine kullanılacak vcpkg dizinini belirtin.

### <a name="upgrade-example"></a>Yükseltme örneği

Aşağıdaki örnekte, yalnızca belirtilen kitaplıkların nasıl yükseltilen gösterilmektedir. vcpkg gerektiğinde bağımlılıkları otomatik olarak çeker.

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

## <a name="contribute-new-libraries"></a>Yeni kitaplıklar ala

Özel bağlantı noktaları koleksiyonunuza istediğiniz kitaplıkları ekleyebilirsiniz. Genel katalog için yeni bir kitaplık önermek için [GitHub vcpkg sorunu sayfasında](https://github.com/Microsoft/vcpkg/issues)bir sorun açın.

## <a name="remove-a-library"></a>Kitaplığı kaldırma

Yüklü bir kitaplığı kaldırmak için **vcpkg kaldır** yazın. Başka kitaplıklar buna bağlıysa, tüm akış altkitaplıkların kaldırılmasına neden olan **-recurse**( yeniden lanetle) komutunu yeniden çalıştırmanız istenir.

## <a name="customize-vcpkg"></a>Vcpkg'yi özelleştir

Vcpkg klonunuzu istediğiniz şekilde değiştirebilirsiniz. Hatta birden çok vcpkg klonlar oluşturabilir, sonra her birinde portdosyaları değiştirebilirsiniz. Bu, belirli kitaplık sürümlerini elde etmenin veya belirli komut satırı parametrelerini belirtmenin basit bir yoludur. Örneğin, bir kuruluşta, tek tek geliştirici grupları gruplarına özgü bir bağımlılık kümesine sahip yazılımlar üzerinde çalışabilir. Çözüm, her takım için bir vcpkg klonu kurmaktır. Ardından, kitaplık sürümlerini karşıdan yükleyecek ve her takımın ihtiyaç duyduğu derleme anahtarlarını ayarlamak için klonları değiştirin.

## <a name="uninstall-vcpkg"></a>Vcpkg'ı kaldır

Vcpkg dizinini silmeniz için. Bu dizin siler vcpkg dağıtımını ve vcpkg'ın yükettiği tüm kitaplıkları yükler.

## <a name="send-feedback-about-vcpkg"></a>vcpkg hakkında geri bildirim gönderin

Hata raporları ve özellikler için öneriler de dahil olmak üzere vcpkg hakkında Microsoft'a geri bildirim göndermek için **vcpkg kişisi --anket** komutunu kullanın.

## <a name="the-vcpkg-folder-hierarchy"></a>vcpkg klasör hiyerarşisi

Tüm vcpkg işlevselliği ve verileri, "örnek" adı verilen tek bir dizin hiyerarşisinde bağımsızdır. Kayıt defteri ayarları veya çevre değişkenleri yok. Bir makinede herhangi bir sayıda vcpkg örneği olabilir ve bunlar birbirlerine müdahale etmez.

Bir vcpkg örneğinin içeriği şunlardır:

- ağaçlar inşa - her kitaplığın inşa edildiği kaynakların alt klasörlerini içerir
- dokümanlar -- dokümantasyon ve örnekler
- indirilenler -- indirilen araçların veya kaynakların önbelleğe alınmış kopyaları. yükle komutunu çalıştırdığınızda vcpkg burada ilk kez arama yaparken.
- yüklü- Yüklü her kitaplık için üstbilgi ve ikilileri içerir. Visual Studio ile tümleştirdiğinizde, aslında bu klasörü arama yollarına eklemesini söylüyorsunuz.
- paketler -- Yüklemeler arasında evreleme için iç klasör.
- bağlantı noktaları -- Katalogdaki her kitaplığı, sürümünü ve nereden indirilirlerini açıklayan dosyalar. Gerekirse kendi bağlantı noktanızı ekleyebilirsiniz.
- komut dosyaları -- Komut dosyaları (cmake, powershell) vcpkg tarafından kullanılır.
- toolsrc -- vcpkg ve ilgili bileşenler için C++ kaynak kodu
- üçüzler -- Desteklenen her hedef platformun ayarlarını içerir (örneğin, x86-windows veya x64-uwp).

## <a name="command-line-reference"></a>Komut satırı başvurusu

|Komut|Açıklama|
|---------|---------|
|**vcpkg \[arama pat]**|Yüklemek için kullanılabilir paketleri arama|
|**vcpkg \<yükleme pkg>...**|Paket yükleme|
|**vcpkg \<kaldırmak pkg>...**|Paketi kaldırma|
|**vcpkg kaldırmak --eski**|Güncel olmayan tüm paketleri kaldırma|
|**vcpkg listesi**|Yüklü paketleri listele|
|**vcpkg güncelleme**|Güncelleştirmek için paketlerin listesini görüntüleme|
|**vcpkg yükseltme**|Tüm eski paketleri yeniden oluşturma|
|**vcpkg karma \<dosya \[> alg]**|Karma belirli bir algoritma, varsayılan SHA512 tarafından bir dosya|
|**vcpkg entegre yükleme**|Yüklenen paketleri kullanıcı çapında kullanılabilir hale getirin. İlk kullanımda yönetici ayrıcalıkları gerektirir|
|**vcpkg entegre kaldırmak**|Kullanıcı genelinde tümleştirmeyi kaldırma|
|**vcpkg entegre proje**|Bireysel VS proje kullanımı için referans nuGet paketi oluşturma|
|**vcpkg \<ihracat pkg>... \[opt]...**|Paketi dışarı aktarma|
|**vcpkg edit \<pkg>**|Düzenleme için bir bağlantı noktası açın (%EDITOR%, varsayılan 'kod' kullanır)|
|**vcpkg \<oluşturmak pkg \< \[> url> archivename]**|Yeni bir paket oluşturma|
|**vcpkg önbellek**|Önbelleğe alınmış derlenmiş paketleri listele|
|**vcpkg sürümü**|Sürüm bilgilerini görüntüleme|
|**vcpkg iletişim --anket**|Geri bildirim göndermek için kişi bilgilerini görüntüleyin.|

### <a name="options"></a>Seçenekler

|Seçenek|Açıklama|
|---------|---------|
|**--üçüz \<t>**|Hedef mimari üçüz belirtin. (varsayılan: `%VCPKG_DEFAULT_TRIPLET%`, ayrıca **vcpkg yardım üçüz**bakınız )|
|**--vcpkg-kök \<yolu>**|vcpkg kök dizinini belirtin `%VCPKG_ROOT%`(varsayılan: )|
