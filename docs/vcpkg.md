---
title: "vcpkg--Windows için bir C++ Paket Yöneticisi | Microsoft Docs"
description: "vcpkg edinme ve açık kaynaklı C++ kitaplıkları Windows yüklemesini büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir."
keywords: vcpkg
author: mikeblome
ms.author: mblome
ms.date: 05/30/2017
ms.technology: cpp-ide
ms.tgt_pltfrm: windows
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.topic: article
dev_langs: C++
manager: ghogen
ms.openlocfilehash: de5825e64abac210561cb8cbe0dc3320a740cbee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="vcpkg-c-package-manager-for-windows"></a>vcpkg: Windows için C++ Paket Yöneticisi 
vcpkg edinme ve yükleme Windows üçüncü taraf kitaplıkların büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir. Projenizi üçüncü taraf kitaplıkları kullanıyorsa, bunları yüklemeye vcpkg kullanmanızı öneririz. vcpkg hem açık kaynak hem de özel kitaplıkları destekler. Vcpkg genel katalogdaki tüm kitaplıkları Visual Studio 2015 ve Visual Studio 2017 ile uyumluluk için test edilmiştir. C++ topluluk sürekli olarak daha fazla kitaplık ekleme ve May 2017 itibariyle katalogda üzerinde 238 kitaplıkları vardır.

## <a name="simple-yet-flexible"></a>Basit ancak esnek
Tek bir komutla kaynakları indirmek ve kitaplık oluştur. vcpkg kendisi bir açık kaynak projesi, GitHub üzerinde kullanılabilir değildir. Özel, clone(s), örneğin farklı kitaplıkları veya hangi genel Kataloğu'nda bulunan daha kitaplıklarının farklı sürümlerini belirterek gibi herhangi bir şekilde özelleştirebilirsiniz. Tek bir makinede vcpkg, birden çok klonlar olabilir, kitaplıklar ve/veya derleme anahtarlar vb. her biri özel oluşturan ayarlar. Her kopya tamamen kendi içinde bulunan, x copyable kendi kopyasıyla birlikte yalnızca kendi hiyerarşisi üzerinde çalışır vcpkg.exe, ortamıdır. vcpkg tüm ortam değişkenlerini eklenmez ve Windows kayıt defteri veya Visual Studio üzerinde hiçbir bağımlılık içeriyor.

## <a name="sources-not-binaries"></a>Kaynakları değil ikili dosyalar
Genel katalogdaki kitaplıkları için ikili dosyaları [1] yerine kaynakları vcpkg indirir. 2017 yüklü değilse, Visual Studio 2017 ya da Visual Studio 2015 kullanarak bu kaynakları derler. Uygulama kodu gibi bu bağlantılarını C++'da, kullandığınız kitaplıkları aynı derleyici ve derleyici sürümü ile derlendiğini çok önemlidir. Vcpkg kullanarak kaldırın veya eşleşmeyen ikili dosyaları ve sorunlara neden olabilir olası en büyük ölçüde azaltabilir. Visual C++ derleyicisi belirli bir sürümünü standartlaştırılmış takımların bir ekip üyesine vcpkg kaynakları indirmek ve ikili dosyaları kümesini derlemek ve diğer takım üyeleri için ikili dosyaları ve üstbilgileri ZIP Dışa Aktar komutunu kullanmak için kullanabilirsiniz. Daha fazla bilgi için ikili dosyaları ve üstbilgileri aşağıdaki verme derlenmiş bakın. 

Bağlantı noktaları koleksiyonundaki özel kitaplıklarla vcpkg kopya oluşturursanız, önceden oluşturulmuş ikili dosyaları ve üst bilgileri indirmeleri bir bağlantı noktası eklemek ve yalnızca değişen dosyaları istenilen konuma kopyalayan bir portfile.cmake dosyası yazma.

[1] *Not: özel bazı kitaplıklar için kaynakları kullanılabilir değil. Vcpkg bu gibi durumlarda uyumlu önceden oluşturulmuş ikili dosyaları indirir.*

## <a name="installation"></a>Yükleme
Github'dan vcpkg depoyu kopyalama: https://github.com/Microsoft/vcpkg. Tercih ettiğiniz herhangi bir klasör konumuna indirebilirsiniz.

Önyükleyici kök klasöründe çalıştır: önyükleme vcpkg.bat.

## <a name="basic-tasks"></a>Basit görevler
  
### <a name="search-the-list-of-available-libraries"></a>Kullanılabilir kitaplık listesini arama
Komut isteminde, hangi paketlerin kullanılabilir görmek için:`vcpkg search`

Bu komut vcpkg/bağlantı noktalarını klasörlerdeki denetim dosyaları sıralar. Böyle bir listesini görürsünüz:

```cmd
ace       6.4.3   The ADAPTIVE Communication Environment
anax      2.1.0-1 An open source C++ entity system. <https://github...
antlr4    4.6-1   ANother Tool for Language Recognition
apr       1.5.2   The Apache Portable Runtime (APR) is a C library ...
asio      1.10.8  Asio is a cross-platform C++ library for network ...
assimp    3.3.1   The Open Asset import library
atk       2.24.0  GNOME Accessibility Toolkit
...
```

  Örneğin, bir model üzerinde filtre `vcpkg search ta`:

```cmd
botan       2.0.1      A cryptography library written in C++11
portaudio   19.0.6.00  PortAudio Portable Cross-platform Audio I/O API P...
taglib      1.11.1-2   TagLib Audio Meta-Data Library

```

### <a name="install-a-library-on-your-local-machine"></a>Bir kitaplık yerel makinenize yükleyin
Kullanarak bir kitaplığı adını aldıktan sonra `vcpkg search`, kullandığınız `vcpkg install` kitaplığı indirin ve derleyin için. vcpkg kitaplığın portfile bağlantı noktalarını dizininde kullanır. Hiçbir Üçlü belirtilirse, vcpkg yükleyin ve x86 windows derleyin. Portfile bağımlılıkları belirtiyorsa, vcpkg indirin ve bu da yükleyin. İndirdikten sonra vcpkg kitaplığı ne olursa olsun sistem kitaplığı kullanıp yapı kullanarak oluşturur. CMake ve MSBuild proje dosyalarını tercih edilir, ancak başka bir yapı sistemi ile birlikte desteklenen olun. Yerel makinede vcpkg belirtilen yapı sistem bulamazsanız, indirin ve yükleyin.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
```

### <a name="list-the-libraries-already-installed"></a>Zaten yüklü kitaplıkları Listele
Bazı kitaplıklar yükledikten sonra kullanabileceğiniz `vcpkg list` ne olduğunu görmek için:

```cmd
> vcpkg list

boost:x86-windows       1.64-3   Peer-reviewed portable C++ source libraries
bzip2:x86-windows       1.0.6-1  High-quality data compressor.
cpprestsdk:x86-windows  2.9.0-2  C++11 JSON, REST, and OAuth library The C++ REST ...
openssl:x86-windows     1.0.2k-2 OpenSSL is an open source project that provides a...
websocketpp:x86-windows 0.7.0    Library that implements RFC6455 The WebSocket Pro...
zlib:x86-windows        1.2.11   A compression library
```

### <a name="integrate-with-visual-studio"></a>Visual Studio ile tümleştirme
#### <a name="per-user"></a>Kullanıcı başına
Çalıştırma `vcpkg integrate install` VC ++ dizinleri yollarını el ile düzenleme için gerek kalmadan kullanıcı başına temelinde tüm vcpkg üstbilgi dosyaları ve ikili dosyaları bulmak için Visual Studio yapılandırmak için. Birden çok klonlar varsa, bu komutu çalıştırmak kopya yeni varsayılan konum haline gelir.

Artık # üst bilgiler klasör/üst yazarak include ve otomatik tamamlama yardımcı olacaktır. Kitaplıklar için bağlama veya proje başvuruları ekleme için hiçbir ek adımlar gereklidir. Visual Studio azure depolama cpp üstbilgileri nasıl bulacağını aşağıda gösterilmektedir. vcpkg kendi üstbilgileri hedef platformu tarafından bölümlenmiş \installed alt yerleştirir. Aşağıdaki diyagramda INCLUDE dosyaların listesini gösterir `/was` alt kitaplığı:

 ![vcpkg IntelliSense tümleştirme](media/vcpkg-intellisense.png "vcpkg ve IntelliSense")  

#### <a name="per-project"></a>Proje
Etkin vcpkg Örneğinizde sürümünden farklı bir kitaplık belirli bir sürümünü kullanmanız gerekiyorsa, vcpkg yeni bir kopya yapmak, gerekir ve ardından Çalıştır'ın sürümünü edinmek için kitaplık portfile Değiştir `vcpkg install <library>`. Bundan sonra kullanabileceğiniz `vcpkg integrate project` bu kitaplığı proje başına temelinde başvuruda bulunan bir NuGet paketi oluşturmak için.

### <a name="export-compiled-binaries-and-headers"></a>Derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma
Karşıdan yükle ve kitaplıkları oluşturmak için bir takımındaki gerektiren verimsiz olabilir. Tek bir takım üyesine o iş yapın ve ardından `vcpkg export` ikili dosyaları ve diğer ekip üyeleriyle kolaylıkla paylaşılabilir üstbilgileri bir zip dosyası oluşturmak için. 

### <a name="update-installed-libraries"></a>Güncelleştirmenin yüklü kitaplıkları
Genel katalog kitaplıkları en son sürümleri ile güncel tutulur. Yerel Kitaplıklarınızı hangisinin güncel olduğunu belirlemek için kullanın `vcpkg update`. Bağlantı noktaları koleksiyonunuzu genel katalog en son sürüme güncelleştirmek hazır olduğunuzda, yalnızca github deposuna yönelik bir git çekme işlemi yapın veya yeni bir kopya oluşturun ve hala gerekliyse eskisinin tutun.

### <a name="contribute-new-libraries"></a>Yeni kitaplıkları katkıda bulunan
Özel bağlantı noktaları koleksiyonunuzda gibi kitaplıkları içerebilir. Genel Katalog için yeni bir kitaplık önermek için 


### <a name="remove-a-library"></a>Bir kitaplık Kaldır
Tür `vcpkg remove` yüklü bir kitaplığını kaldırmak için. Diğer kitaplıkları bağımlı ise, komutu yeniden çalıştırarak istenir `--recurse`, kaldırılacak tüm aşağı akış kitaplıkları neden olacak.

### <a name="customize-vcpkg"></a>Vcpkg özelleştirme
İstediğiniz herhangi bir şekilde vcpkg kopyasını değiştirebilirsiniz. Birden çok vcpkg klonlar oluşturabilir ve portfiles kitaplıkları belirli sürümlerini edinmek veya komut satırı parametrelerini belirtmek için her biri olarak değiştirebilirsiniz. Örneğin, kuruluş, geliştiricilerin bir grup bir dizi bağımlılıkları olan yazılımı çalışıyor olabilirsiniz ve başka bir grubu farklı bir kümesi olabilir. İki vcpkg klonlar ayarlamak ve kitaplıklar ve derleme anahtarlar vb., sürümleri karşıdan yüklemek için her biri gereksinimlerinize göre değiştirin. 

## <a name="the-vcpkg-folder-hierarchy"></a>Vcpkg klasör hiyerarşisi
Tüm vcpkg işlevselliği ve verileri tek bir dizin hiyerarşisinde tamamen kendi içinde bulunan; Bu, bir "örnek" adı verilir. Kayıt defteri ayarları veya ortam değişkenleri yok. Bir makinede herhangi bir sayıda vcpkg örneklerini sahip olabilir ve birbirleri ile etkilemeyecektir. 

Bir vcpkg örneği içeriğini şunlardır: 
- buildtrees--içeren alt her kitaplık yerleşik olan kaynakları
- belgeleri--belgeler ve örnekler
- indirme--indirilen araçları veya kaynakları önbelleğe alınan kopyaları. yükleme komutunu çalıştırdığınızda vcpkg burada ilk arar.
- yüklü--üstbilgiler ve yüklü her kitaplık için ikili dosyalarını içerir. VIsual Studio ile tümleştirdiğinizde, aslında bu söylemiş olursunuz bu klasör, arama yolları ekleyin.
- paketleri--hazırlama arasında iç klasörü yükler.
- bağlantı noktaları--Kataloğu, sürümü ve indirme nereden her kitaplıkta açıklamak dosyaları. Gerekirse, kendi bağlantı noktaları ekleyebilirsiniz.
- komut dosyaları--vcpkg tarafından kullanılan komut dosyaları (cmake, powershell).
- toolsrc--vcpkg ve ilgili bileşenler için C++ kaynak kodu
- triplets--her desteklenen hedef Platformu (örneğin x86 windows veya x64 uwp) için ayarları içerir.

## <a name="command-line-reference"></a>Komut satırı başvurusu
- vcpkg arama [pat] paketleri oluşturulacak arayın
- vcpkg yükleme <pkg>...    Paket yükleme
- vcpkg kaldırmak <pkg>...  Bir paketi kaldırma
- eski vcpkg--kaldırmak tüm güncel olmayan paketler
- vcpkg listesi yüklü listesinde paketleri
- vcpkg güncelleştirmek için güncelleştirme paketleri listesini görüntüle
- vcpkg karma <file> [algoritma] belirli algoritması tarafından bir dosya karma, SHA512 varsayılan
- vcpkg yükleme yapma yüklü paketleri kullanılabilir kullanıcı genelinde tümleştirin. İlk kullanımda yönetici ayrıcalıkları gerektirmez
- vcpkg tümleştirmek Kaldır Kaldır kullanıcı genelinde tümleştirme
- vcpkg tümleştirmek proje oluştur başvuruda bulunan bir nuget paketi tek tek VS proje kullanmak için
- vcpkg verme <pkg>... [opt]...    Bir paket dışarı aktarmalar
- vcpkg düzenleme <pkg> (kullanır Düzenleyicisi %, varsayılan 'code') düzenlemek için bir bağlantı noktasını açın
- vcpkg alma <pkg> önceden oluşturulmuş bir kitaplık alma
- vcpkg oluşturma <pkg> <url> [archivename] yeni paketi oluştur
- vcpkg sahibi <pat> yüklü paketleri dosyalarında arayın
- vcpkg önbellek listesi önbelleğe alınan derlenmiş paketleri
- vcpkg sürüm sürüm bilgilerini görüntüle
- vcpkg başvurun geri bildirim göndermek için kişi bilgilerini görüntüleme

### <a name="options"></a>Seçenekler:
  **`--triplet <t>`**Hedef mimari Üçlü belirtin. (varsayılan: `%VCPKG_DEFAULT_TRIPLET%`, ayrıca bkz. `vcpkg help triplet`)

  **`--vcpkg-root <path>`**Vcpkg kök dizini belirtin (varsayılan: `%VCPKG_ROOT%`)
