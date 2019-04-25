---
title: vcpkg--bir C++ için Paket Yöneticisi Windows, Linux ve MacOS
description: vcpkg edinme ve yükleme, açık kaynaklı C++ kitaplıklarının Windows üzerinde büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir.
author: mikeblome
ms.author: mblome
ms.date: 03/18/2019
ms.technology: cpp-ide
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.openlocfilehash: 2ca1b88f492d96f8a08d296cab7f35f3b72409c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314625"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Windows, Linux ve MacOS için C++ Paket Yöneticisi

vcpkg edinme ve yükleme Windows, Linux ve Macos'ta üçüncü taraf kitaplıkların büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir. Projeniz üçüncü taraf kitaplıklarını kullanıyorsa, bunları yüklemek için vcpkg kullanmanızı öneririz. vcpkg hem açık kaynak hem de özel kütüphanelerini destekler. Vcpkg Windows katalogdaki tüm kitaplıkları Visual Studio 2015 ve Visual Studio 2017 ile uyumluluk için test edilmiştir. Mayıs 2018'den itibaren Windows kataloğunda ve Linux/MacOS kataloğunda 350 üzerinden 900 kitaplıkları vardır. C++ topluluğu, her iki kataloglarında düzenli olarak daha fazla kitaplıkları eklemektir.

## <a name="simple-yet-flexible"></a>Basit ancak esnek

Tek bir komutla kaynakları indirmek ve bir kitaplık oluşturun. vcpkg kendisini Github'da bulunan bir açık kaynak projesi olan. Kendi özel clone(s) istediğiniz herhangi bir şekilde özelleştirebilirsiniz. Örneğin, farklı kitaplıkları veya genel kataloğunda bulduğu daha kitaplıkların farklı sürümleri belirtebilirsiniz. Tek bir makinede birden fazla klonlarını vcpkg olabilir, kitaplıkları ve/veya derleme anahtarları, vb. her biri özel üretme ayarlar. Her kopya yalnızca kendi hiyerarşisini çalışır vcpkg.exe kendi kopyalama ile kendi içinde bir ortam büyüktür. vcpkg herhangi bir ortam değişkenini eklenmez ve Windows kayıt defteri veya Visual Studio bağımlılığı yoktur.

## <a name="sources-not-binaries"></a>Kaynakları değil ikili dosyaları

Windows kataloğunda kitaplıkları için ikili dosyaları [1] yerine kaynakları vcpkg indirir. Bu, bu kaynakları 2017 yüklü değilse Visual Studio 2017 veya Visual Studio 2015'i kullanarak derler. Uygulama kodu olarak bağlanan, C++'da, kullandığınız tüm kitaplıkları aynı derleyici ve derleyici sürümü ile derlendiğini çok önemlidir. Vcpkg'ı kullanarak kaldırın veya eşleşmeyen ikili dosyaları ve sorunlara neden olabilir olası en az önemli ölçüde azaltabilir. Bir derleyici belirli bir sürümü üzerinde standartlaştırılmıştır teams'de, bir takım üyesinin kaynakları indirmek ve bir dizi ikili dosyaları derlemek ve ardından export komutu ikili dosyaları ve üstbilgi diğer ekip üyeleri ZIP vcpkg kullanabilirsiniz. Daha fazla bilgi için [dışarı aktarma derlenmiş ikili dosyaları ve üstbilgi](#export_binaries_per_project) aşağıda.

Özel bağlantı noktaları koleksiyonu kitaplıkları ile vcpkg kopya oluşturma, önceden oluşturulmuş ikili dosyalar ve üstbilgi indiren bir bağlantı noktasını ekleyin ve yalnızca bu dosyaları istenilen konuma kopyalar. bir portfile.cmake dosyasına yazılamıyor.

[1] *Not: bazı özel kitaplıkları için kaynakları kullanılabilir değil. Vcpkg bu gibi durumlarda önceden oluşturulmuş uyumlu ikili dosyaları indirir.*

## <a name="installation"></a>Yükleme

Github'dan vcpkg deposunu kopyalayın: [ https://github.com/Microsoft/vcpkg ](https://github.com/Microsoft/vcpkg). Tercih ettiğiniz herhangi bir klasör konumuna indirebilirsiniz.

Önyükleyici kök klasöründe çalıştırın:

- **önyükleme vcpkg.bat** (Windows)
- **./Bootstrap-vcpkg.sh** (Linux, MacOS)

## <a name="search-the-list-of-available-libraries"></a>Kullanılabilir kitaplıkları listesinde arama yapın

Komut isteminde, hangi paketleri kullanılabildiğini görmek için: **vcpkg arama**

Bu komutu vcpkg/bağlantı noktası alt denetim dosyaları listeler. Böyle bir listesini görürsünüz:

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

Örneğin, bir model üzerinde filtre **vcpkg arama eri**:

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library
```

### <a name="install-a-library-on-your-local-machine"></a>Bir kitaplık yerel makinenize yükleyin.

Kullanarak bir kitaplık adını aldıktan sonra **vcpkg arama**, kullandığınız **vcpkg yükleme** için Kitaplığı'nı indirin ve derleyin. vcpkg kitaplığın portfile bağlantı noktaları dizinde kullanır. Hiçbir Üçlü belirtilmişse vcpkg yüklemek ve derlemek için hedef platform için varsayılan Üçlü: x86 windows, x64 linux.cmake veya x64 osx.cmake.

Linux kitaplıkları için yerel makinede yüklenen gcc vcpkg bağlıdır. MacOS üzerinde vcpkg Clang kullanır.

Portfile bağımlılıkları belirtiyorsa, vcpkg indirir ve bu da yükler. İndirdikten sonra her yapı sistemi kitaplığı kullanan kullanarak vcpkg kitaplığı oluşturur. CMake ve (Windows) MSBuild projeleri, tercih edilen, ancak yapma, herhangi bir yapı sistemiyle birlikte desteklenir. Vcpkg yerel makinede belirtilen derleme sistemi bulamazsanız indirir ve yükler.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

CMAKE projeleri için CMAKE_TOOLCHAIN_FILE kitaplıkları ile kullanılabilir hale getirmek için kullanın. `find_package()`. Örneğin:

```cmd
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg/scripts/buildsystems/vcpkg.cmake (Linux/MacOS)
cmake .. -DCMAKE_TOOLCHAIN_FILE=vcpkg\scripts\buildsystems\vcpkg.cmake (Windows)
```

## <a name="list-the-libraries-already-installed"></a>Zaten yüklü kitaplıkları Listele

Bazı kitaplıklar yükledikten sonra kullanabileceğiniz **vcpkg listesi** ne olduğunu görmek için:

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

## <a name="integrate-with-visual-studio-windows"></a>Visual Studio (Windows) ile tümleştirin

### <a name="per-user"></a>Kullanıcı başına

Çalıştırma **vcpkg tümleştirme yükleme** VC ++ dizinleri yollarını el ile düzenlemek için gerek kalmadan kullanıcı başına temelinde tüm vcpkg başlık dosyaları ve ikili dosyaları bulmak için Visual Studio yapılandırmak için. Birden çok kopyada varsa, bu komutu çalıştırmanız kopya varsayılan konuma haline gelir.

Artık # klasör/üst bilgi yazarak üst bilgileri include ve otomatik tamamlama, yardımcı olur. Kitaplıklar için bağlama veya proje başvurularının eklenmesi için ek adımlar gereklidir. Visual Studio azure depolama cpp üstbilgileri nasıl bulacağını aşağıda gösterilmiştir. vcpkg yerleştirir, üst bilgilerinde **/ yüklü** alt, hedef platforma göre bölümlenir. Dahil etme dosyalarında listesi aşağıdaki diyagramda gösterilmiştir **/ was'da** alt kitaplığı:

![vcpkg IntelliSense tümleştirme](media/vcpkg-intellisense.png "vcpkg ve IntelliSense")

### <a name="per-project"></a>Proje

Etkin vcpkg Örneğinizdeki sürümünden farklı bir kitaplık belirli bir sürümünü kullanmanız gerekiyorsa, aşağıdaki adımları izleyin:

1. Vcpkg yeni bir kopyasını olun
1. İhtiyacınız olan sürümü almak kitaplığı portfile değiştirme
1. Çalıştırma **vcpkg yükleme \<kitaplığı >**.
1. Kullanım **vcpkg tümleştirme proje** bu kitaplığı proje başına temelinde başvuran bir NuGet paketi oluşturmak için.

## <a name="integrate-with-visual-studio-code-linuxmacos"></a>Visual Studio kodu (Linux/MacOS) ile tümleştirme

Çalıştırma **vcpkg tümleştirme yükleme** Visual Studio Code, Linux/Macos'ta vcpkg enlistement konumu ile yapılandırın ve kaynak dosyaları üzerinde IntelliSense etkinleştirmek için.

## <a name="target-linux-from-windows-via-wsl"></a>Hedef Linux'taki WSL aracılığıyla Windows

Linux (WSL) için Windows alt sistemi kullanarak bir Windows makineden Linux ikili dosyaları oluşturabilir. Yönergelerini izleyin [Windows 10 WSL ayarlama](/windows/wsl/install-win10)ve onunla yapılandırma [Linux için Visual Studio Uzantısı](https://blogs.msdn.microsoft.com/vcblog/2017/02/08/targeting-windows-subsystem-for-linux-from-visual-studio/). Tüm yerleşik kitaplıkları hem Windows hem de Linux için aynı klasöre yerleştirin ve hem Windows hem de WSL erişin.

## <a name="export_binaries_per_project"></a> Derlenmiş ikili dosyalar ve üst bilgileri verme

İndirin ve kitaplıkları oluşturmak için bir takımındaki gerektiren verimsiz olabilir. Tek bir takım üyesi, iş yapın ve ardından **vcpkg dışarı aktarma** diğer ekip üyeleriyle kolaylıkla paylaşılabilen bir zip dosyası ikili dosyaları ve üstbilgi ya da (çeşitli biçimlendirme kullanılabilir), bir NuGet paketi oluşturmak için.

## <a name="updateupgrade-installed-libraries"></a>Yüklü güncelleştirileceğine/yükseltileceğine kitaplıkları

Genel katalog kitaplıklarının en son sürümlerini ile güncel tutulur. Yerel kitaplıklarınızın güncel olan belirlemek için **vcpkg güncelleştirme**. Bağlantı noktaları koleksiyonunuz Genel Kataloğu'nun en son sürüme güncelleştirmek hazır olduğunuzda, çalıştırma **vcpkg yükseltme** otomatik olarak indirmek ve güncel Kitaplıklarınızı yüklü bir bölümünü veya tamamını yeniden derlemek için komutu.

Varsayılan olarak, **yükseltme** komutu, yalnızca güncel kitaplıkları listeler; bunları yükseltmez. Yükseltmeyi gerçekleştirmek için kullanın **--no-prova** seçeneği.

```cmd
  vcpkg upgrade --no-dry-run
```

### <a name="upgrade-options"></a>Yükseltme seçenekleri

- **--no-prova** yükseltin; belirtilmediğinde komutu yalnızca güncel olmayan paketleri listeler.
- **--Canlı devam eden** biri başarısız olsa bile paketler yüklemeye devam et.
- **--Üçlü \<t >** nitelenmemiş paketleri için varsayılan Üçlü ayarlayın.
- **--vcpkg kök \<yolu >** geçerli dizini veya aracı dizin yerine kullanılacak vcpkg dizini belirtin.

### <a name="upgrade-example"></a>Yükseltme örneği

Aşağıdaki örnek, yalnızca belirtilen kitaplıkları sürümüne yükseltme yapmayı gösterir. Bu vcpgk bağımlılıkları gerektiği şekilde otomatik olarak çeker. unutmayın.

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

## <a name="contribute-new-libraries"></a>Yeni kitaplıkları katkıda bulunun

Özel bağlantı noktaları koleksiyonunuzda istediğiniz tüm kitaplıkları dahil edebilirsiniz. Genel Katalog için yeni bir kitaplık önermek için bir sorun açın [GitHub vcpkg sorunu sayfa](https://github.com/Microsoft/vcpkg/issues).

## <a name="remove-a-library"></a>Bir kitaplık Kaldır

Tür **vcpkg Kaldır** yüklü bir kitaplığını kaldırmak için. Diğer bir kitaplıklarına bağımlı, komutu yeniden istenir **--recurse**, tüm aşağı akış kitaplıklarının kaldırılması neden olur.

## <a name="customize-vcpkg"></a>Vcpkg özelleştirme

Vcpkg istediğiniz herhangi bir şekilde, bir kopyasını değiştirebilirsiniz. Birden çok vcpkg kopyaları oluşturabilir ve portfiles kitaplıkları belirli sürümlerini edinmek veya komut satırı parametreleri belirtmek için her biri olarak değiştirin. Örneğin, kuruluş, geliştiricilerin bir grup kümesi bağımlılıkları olan yazılımı çalışıyor olabilirsiniz ve başka bir grup farklı olabilir. Vcpkg iki klonlarını ayarlayabilir ve her biri, kitaplıklar ve derleme anahtarlar vb., sürümlerini indirmek için ihtiyaçlarınıza göre değiştirin.

## <a name="uninstall-vcpkg"></a>Vcpkg kaldırma

Dizin silmeniz yeterlidir.

## <a name="send-feedback-about-vcpkg"></a>Vcpkg hakkında geri bildirim gönderin

Kullanım **vcpkg kişi--anket** komutu vcpkg hata raporlarını ve özellikler için öneriler de dahil olmak üzere hakkında Microsoft'a geri bildirim göndermek için.

## <a name="the-vcpkg-folder-hierarchy"></a>Vcpkg klasör hiyerarşisi

Tüm vcpkg işlevleri ve verileri "örnek" olarak adlandırılan tek bir dizin hiyerarşisinde müstakil. Kayıt defteri ayarları veya ortam değişkenlerini yoktur. Vcpkg örneklerini herhangi bir sayıda bir makineye sahip olabilir ve birbiriyle karışmaz.

Vcpkg örneği içeriğini şunlardır:

- buildtrees--içeren alt her kitaplık içinden yerleşik kaynaklar
- docs--belgeler ve örnekler
- indirmeler--indirilen araçları ya da kaynakları ön belleğe alınmış kopyalarını. yükleme komutunu çalıştırdığınızda vcpkg burada ilk arar.
- yüklü--üst bilgiler ve ikili dosyaları yüklü her kitaplığı içerir. Visual Studio ile tümleştirdiğinizde, aslında bu söylüyoruz bu klasör, arama yollarını ekleyin.
- paketleri--iç arasında Hazırlama klasörü yükler.
- bağlantı noktaları--her kitaplık Kataloğu, sürümü ve indirmek üzere nerede açıklayan dosyaları. Gerekirse kendi bağlantı noktaları ekleyebilirsiniz.
- betikleri--vcpkg tarafından kullanılan betikler (cmake, powershell).
- toolsrc--vcpkg ve ilgili bileşenler için C++ kaynak kodu
- triplets--her desteklenen hedef Platformu (örneğin, windows x86 veya x64 uwp) için ayarları içerir.

## <a name="command-line-reference"></a>Komut satırı başvurusu

|Komut|Açıklama|
|---------|---------|
|**vcpkg arama [yol]**|Paketleri yüklemek kullanılabilir Ara|
|**vcpkg yükleme \<pkg >...**|Paket yükleme|
|**vcpkg kaldırmak \<pkg >...**|Bir paketi Kaldır|
|**vcpkg Kaldır--güncel değil**|Güncel olmayan tüm paketleri kaldırın|
|**vcpkg listesi**|Kurulu paketleri listelemek|
|**vcpkg güncelleştirme**|Güncelleştirme paketleri listesini görüntüle|
|**vcpkg yükseltme**|Güncel olmayan tüm paketleri yeniden oluşturun|
|**vcpkg karma \<Dosya > [algoritma]**|Belirli bir algoritma tarafından dosya karma, SHA512 varsayılan|
|**vcpkg yükleme tümleştirin**|Yüklü olduğundan kullanıcı genelinde kullanılabilir paketler. İlk kullanımda yönetici ayrıcalıkları gerektirmez|
|**vcpkg tümleştirme Kaldır**|Kullanıcı genelinde tümleştirmeyi Kaldır|
|**vcpkg proje tümleştirin**|VS proje kullanımları için başvuruda bulunan bir NuGet paketi oluştur|
|**vcpkg dışarı aktarma \<pkg >... [iyileştirilmiş]...**|Bir paketi Dışarı Aktar|
|**vcpkg düzenleme \<pkg >**|(Kullanımlar % Düzenleyicisi %, varsayılan 'code') düzenlemek için bir bağlantı noktası açık|
|**vcpkg oluşturma \<pkg > \<URL'si > [archivename]**|Yeni bir paket oluşturun|
|**vcpkg önbellek**|Paketleri listesi önbelleğe alınan derlenmiş|
|**vcpkg sürümü**|Sürüm bilgilerini görüntüle|
|**vcpkg kişi--anketi**|Geri bildirim göndermek için iletişim bilgilerini görüntüleme.|

### <a name="options"></a>Seçenekler

|Seçenek|Açıklama|
|---------|---------|
|**--Üçlü \<t >**|Hedef mimari Üçlü belirtin. (varsayılan: `%VCPKG_DEFAULT_TRIPLET%`, ayrıca bkz: **vcpkg Yardım Üçlü**)|
|**--vcpkg kök \<yolu >**|Vcpkg kök dizini belirtin (varsayılan: `%VCPKG_ROOT%`)|
