---
title: vcpkg--Windows için bir C++ Paket Yöneticisi | Microsoft Docs
description: vcpkg edinme ve açık kaynaklı C++ kitaplıkları Windows yüklemesini büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir.
keywords: vcpkg
author: mikeblome
ms.author: mblome
ms.date: 04/06/2018
ms.technology:
- cpp-ide
ms.tgt_pltfrm: windows
ms.assetid: f50d459a-e18f-4b4e-814b-913e444cedd6
ms.topic: article
dev_langs:
- C++
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54d1f0cf2a6971435858a1a64bf3e163631822b5
ms.sourcegitcommit: 0523c88b24d963c33af0529e6ba85ad2c6ee5afb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/08/2018
---
# <a name="vcpkg-c-package-manager-for-windows"></a>vcpkg: Windows için C++ Paket Yöneticisi

vcpkg edinme ve yükleme Windows üçüncü taraf kitaplıkların büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir. Projenizi üçüncü taraf kitaplıkları kullanıyorsa, bunları yüklemeye vcpkg kullanmanızı öneririz. vcpkg hem açık kaynak hem de özel kitaplıkları destekler. Vcpkg genel katalogdaki tüm kitaplıkları Visual Studio 2015 ve Visual Studio 2017 ile uyumluluk için test edilmiştir. C++ topluluk sürekli olarak daha fazla kitaplık ekleme ve Ocak 2018 itibariyle katalogda 600'den fazla kitaplıkları vardır.

## <a name="simple-yet-flexible"></a>Basit ancak esnek

Tek bir komutla kaynakları indirmek ve kitaplık oluştur. vcpkg kendisi bir açık kaynak projesi, GitHub üzerinde kullanılabilir değildir. Özel, clone(s) istediğiniz herhangi bir şekilde özelleştirebilirsiniz. Örneğin, farklı kitaplıkları veya hangi genel Kataloğu'nda bulunan daha kitaplıklarının farklı sürümlerini belirtebilirsiniz. Tek bir makinede vcpkg, birden çok klonlar olabilir, kitaplıklar ve/veya derleme anahtarlar vb. her biri özel oluşturan ayarlar. Her kopya kendi içinde bulunan, x copyable kendi kopyasıyla birlikte yalnızca kendi hiyerarşisi üzerinde çalışır vcpkg.exe, ortamıdır. vcpkg tüm ortam değişkenlerini eklenmez ve Windows kayıt defteri veya Visual Studio üzerinde hiçbir bağımlılık içeriyor.

## <a name="sources-not-binaries"></a>Kaynakları değil ikili dosyalar

Genel katalogdaki kitaplıkları için ikili dosyaları [1] yerine kaynakları vcpkg indirir. 2017 yüklü değilse, Visual Studio 2017 ya da Visual Studio 2015 kullanarak bu kaynakları derler. Uygulama kodu gibi bu bağlantılarını C++'da, kullandığınız kitaplıkları aynı derleyici ve derleyici sürümü ile derlendiğini çok önemlidir. Vcpkg'ı kullanarak kaldırın veya eşleşmeyen ikili dosyaları ve sorunlara neden olabilir olası en büyük ölçüde azaltabilir. Visual C++ derleyicisi belirli bir sürümünü standartlaştırılmış takımların bir ekip üyesine vcpkg kaynakları indirmek ve ikili dosyaları kümesini derlemek ve diğer takım üyeleri için ikili dosyaları ve üstbilgileri ZIP Dışa Aktar komutunu kullanmak için kullanabilirsiniz. Daha fazla bilgi için ikili dosyaları ve üstbilgileri aşağıdaki verme derlenmiş bakın. 

Bağlantı noktaları koleksiyonundaki özel kitaplıklarla vcpkg kopya oluşturursanız, önceden oluşturulmuş ikili dosyaları ve üst bilgileri indirmeleri bir bağlantı noktası eklemek ve yalnızca değişen dosyaları istenilen konuma kopyalayan bir portfile.cmake dosyası yazma.

[1] *Not: özel bazı kitaplıklar için kaynakları kullanılabilir değil. Vcpkg bu gibi durumlarda uyumlu önceden oluşturulmuş ikili dosyaları indirir.*

## <a name="installation"></a>Yükleme

Github'dan vcpkg depoyu kopyalama: https://github.com/Microsoft/vcpkg. Tercih ettiğiniz herhangi bir klasör konumuna indirebilirsiniz.

Önyükleyici kök klasöründe çalıştır: **önyükleme vcpkg.bat**.

## <a name="basic-tasks"></a>Basit görevler

## <a name="search-the-list-of-available-libraries"></a>Kullanılabilir kitaplık listesini arama

Komut isteminde, hangi paketlerin kullanılabilir görmek için: **vcpkg arama**

Bu komut vcpkg/bağlantı noktalarını klasörlerdeki denetim dosyaları sıralar. Böyle bir listesini görürsünüz:

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

### <a name="install-a-library-on-your-local-machine"></a>Bir kitaplık yerel makinenize yükleyin

Kullanarak bir kitaplığı adını aldıktan sonra **vcpkg arama**, kullandığınız **vcpkg yükleme** kitaplığı indirin ve derleyin için. vcpkg kitaplığın portfile bağlantı noktalarını dizininde kullanır. Hiçbir Üçlü belirtilirse, vcpkg yükleyin ve x86 windows derleyin. Portfile bağımlılıkları belirtiyorsa, vcpkg indirir ve bu da yükler. İndirdikten sonra vcpkg kitaplığı ne olursa olsun sistem kitaplığı kullanıp yapı kullanarak oluşturur. CMake ve MSBuild proje dosyalarını tercih edilir, ancak başka bir yapı sistemi ile birlikte desteklenen olun. Yerel makinede vcpkg belirtilen yapı sistem bulamazsanız, indirir ve yükler.

```cmd
> vcpkg install boost:x86-windows

The following packages will be built and installed:
    boost:x86-windows
  * bzip2:x86-windows
  * zlib:x86-windows
Additional packages (*) will be installed to complete this operation.
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

## <a name="integrate-with-visual-studio"></a>Visual Studio ile tümleştirme

### <a name="per-user"></a>Per-user

Çalıştırma **vcpkg tümleştirmek yükleme** VC ++ dizinleri yollarını el ile düzenleme için gerek kalmadan kullanıcı başına temelinde tüm vcpkg üstbilgi dosyaları ve ikili dosyaları bulmak için Visual Studio yapılandırmak için. Birden çok klonlar varsa, bu komutu çalıştırmak kopya yeni varsayılan konum haline gelir.

Artık # klasör/üstbilgi yazarak üst bilgiler include ve otomatik tamamlama, yardımcı olur. Kitaplıklar için bağlama veya proje başvuruları ekleme için hiçbir ek adımlar gereklidir. Visual Studio azure depolama cpp üstbilgileri nasıl bulacağını aşağıda gösterilmektedir. vcpkg yerleştirir kendi üst bilgilerinde **/ yüklü** alt klasörü hedef platformu tarafından bölümlenmiş. Aşağıdaki diyagramda INCLUDE dosyaların listesini gösterir **/ edildi** alt kitaplığı:

![vcpkg IntelliSense tümleştirme](media/vcpkg-intellisense.png "vcpkg ve IntelliSense")

### <a name="per-project"></a>Proje

Etkin vcpkg Örneğinizde sürümünden farklı bir kitaplık belirli bir sürümünü kullanmanız gerekiyorsa, şu adımları izleyin:

1. Vcpkg yeni bir kopya yapmak 
1. İhtiyacınız olan sürümü edinmek için kitaplık portfile değiştirme
1. Çalıştırma **vcpkg yükleme \<kitaplığı >**.
1. Kullanım **vcpkg tümleştirmek proje** bu kitaplığı proje başına temelinde başvuruda bulunan bir NuGet paketi oluşturmak için.

## <a name="export-compiled-binaries-and-headers"></a>Derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma

Karşıdan yükle ve kitaplıkları oluşturmak için bir takımındaki gerektiren verimsiz olabilir. Tek bir takım üyesine o iş yapın ve ardından **vcpkg verme** ikili dosyaları ve diğer ekip üyeleriyle kolaylıkla paylaşılabilir üstbilgileri bir zip dosyası oluşturmak için. 

## <a name="updateupgrade-installed-libraries"></a>Güncelleştirme/yükseltme yüklü kitaplıkları

Genel katalog kitaplıkları en son sürümleri ile güncel tutulur. Yerel Kitaplıklarınızı hangisinin güncel olduğunu belirlemek için kullanın **vcpkg güncelleştirme**. Bağlantı noktaları koleksiyonunuzu genel katalog en son sürüme güncelleştirmek hazır olduğunuzda, çalıştırmak **vcpkg yükseltme** otomatik olarak karşıdan yükle ve güncel Kitaplıklarınızı yüklü bir bölümünü veya tamamını yeniden komutu.

Varsayılan olarak, **yükseltme** komutu yalnızca eski kitaplıkları listeler; bunları yükseltme değil. Yükseltmeyi gerçekleştirmek için kullanın **--çalıştırıp Hayır** seçeneği. 

```cmd
  vcpkg upgrade --no-dry-run 
```

### <a name="upgrade-options"></a>Yükseltme seçenekleri

- **--çalıştırıp Hayır** yükseltmek; belirtilmediğinde komutu yalnızca güncel paketleri listeler. 
- **--Canlı devam eden** başarısız olsa bile paketleri yüklemeye devam et. 
- **--Üçlü \<t >** nitelenmemiş paketler için varsayılan Üçlü ayarlayın. 
- **--vcpkg kök \<yolu >** geçerli dizini veya aracı dizin yerine kullanılacak vcpkg dizini belirtin. 

### <a name="upgrade-example"></a>Yükseltme örneği

### <a name="per-project"></a>Proje
Etkin vcpkg Örneğinizde sürümünden farklı bir kitaplık belirli bir sürümünü kullanmanız gerekiyorsa, şu adımları izleyin:

1. Vcpkg yeni bir kopya yapmak 
1. İhtiyacınız olan sürümü edinmek için kitaplık portfile değiştirme
1. Çalıştırma **vcpkg yükleme \<kitaplığı >**.
1. Kullanım **vcpkg tümleştirmek proje** bu kitaplığı proje başına temelinde başvuruda bulunan bir NuGet paketi oluşturmak için.


## <a name="export-compiled-binaries-and-headers"></a>Derlenmiş ikili dosyaları ve üstbilgileri dışarı aktarma
Karşıdan yükle ve kitaplıkları oluşturmak için bir takımındaki gerektiren verimsiz olabilir. Tek bir takım üyesine o iş yapın ve ardından **vcpkg verme** ikili dosyaları ve diğer ekip üyeleriyle kolaylıkla paylaşılabilir üstbilgileri bir zip dosyası oluşturmak için. 

## <a name="updateupgrade-installed-libraries"></a>Güncelleştirme/yükseltme yüklü kitaplıkları
Genel katalog kitaplıkları en son sürümleri ile güncel tutulur. Yerel Kitaplıklarınızı hangisinin güncel olduğunu belirlemek için kullanın **vcpkg güncelleştirme**. Bağlantı noktaları koleksiyonunuzu genel katalog en son sürüme güncelleştirmek hazır olduğunuzda, çalıştırmak **vcpkg yükseltme** otomatik olarak karşıdan yükle ve güncel Kitaplıklarınızı yüklü bir bölümünü veya tamamını yeniden komutu.

Varsayılan olarak, **yükseltme** komutu yalnızca eski kitaplıkları listeler; bunları yükseltme değil. Yükseltmeyi gerçekleştirmek için kullanın **--çalıştırıp Hayır** seçeneği. 

```cmd
  vcpkg upgrade --no-dry-run 
```

### <a name="upgrade-options"></a>Yükseltme seçenekleri

- **--çalıştırıp Hayır** yükseltmek; belirtilmediğinde komutu yalnızca güncel paketleri listeler. 
- **--Canlı devam eden** başarısız olsa bile paketleri yüklemeye devam et. 
- **--Üçlü \<t >** nitelenmemiş paketler için varsayılan Üçlü ayarlayın. 
- **--vcpkg kök \<yolu >** geçerli dizini veya aracı dizin yerine kullanılacak vcpkg dizini belirtin. 

### <a name="upgrade-example"></a>Yükseltme örneği

Aşağıdaki örnekte, yalnızca belirtilen kitaplıkları yükseltme gösterilmektedir. Bu vcpgk bağımlılıkları gerektiğinde otomatik olarak çeker. unutmayın.

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

## <a name="contribute-new-libraries"></a>Yeni kitaplıkları katkıda bulunan
Özel bağlantı noktaları koleksiyonunuzda gibi kitaplıkları içerebilir. Genel Katalog için yeni bir kitaplık önermek için bir sorun açmak [GitHub vcpkg sorunu sayfası](https://github.com/Microsoft/vcpkg/issues).

## <a name="remove-a-library"></a>Bir kitaplık Kaldır
Tür **vcpkg kaldırmak** yüklü bir kitaplığını kaldırmak için. Diğer kitaplıkları bağımlı, komutu yeniden istenir **--recurse**, kaldırılacak tüm aşağı akış kitaplıkları neden olur.

## <a name="customize-vcpkg"></a>Vcpkg özelleştirme
İstediğiniz herhangi bir şekilde vcpkg kopyasını değiştirebilirsiniz. Birden çok vcpkg klonlar oluşturabilir ve portfiles kitaplıkları belirli sürümlerini edinmek veya komut satırı parametrelerini belirtmek için her biri olarak değiştirebilirsiniz. Örneğin, kuruluş, geliştiricilerin bir grup bir dizi bağımlılıkları olan yazılımı çalışıyor olabilirsiniz ve başka bir grubu farklı bir kümesi olabilir. İki vcpkg klonlar ayarlamak ve kitaplıklar ve derleme anahtarlar vb., sürümleri karşıdan yüklemek için her biri gereksinimlerinize göre değiştirin. 

## <a name="uninstall-vcpkg"></a>Vcpkg kaldırma
Yalnızca dizini silin. 

## <a name="send-feedback-about-vcpkg"></a>Vcpkg hakkında geri bildirim gönder
Kullanım **--anket** hata raporları ve özellikleri için öneri dahil olmak üzere vcpkg hakkında Microsoft'a geri bildirim göndermek için komutu.

## <a name="the-vcpkg-folder-hierarchy"></a>Vcpkg klasör hiyerarşisi
Tüm vcpkg işlevselliği ve verileri bir "örnek" olarak adlandırılan tek bir dizin hiyerarşisinde müstakil. Kayıt defteri ayarları veya ortam değişkenleri yok. Bir makinede herhangi bir sayıda vcpkg örneklerini sahip olabilir ve birbirleri ile karışmaması. 

Bir vcpkg örneği içeriğini şunlardır: 

- buildtrees--içeren alt her kitaplık yerleşik olan kaynakları
- belgeleri--belgeler ve örnekler
- indirme--indirilen araçları veya kaynakları önbelleğe alınan kopyaları. yükleme komutunu çalıştırdığınızda vcpkg burada ilk arar.
- yüklü--üstbilgiler ve yüklü her kitaplık için ikili dosyalarını içerir. Visual Studio ile tümleştirdiğinizde, aslında bu söylemiş olursunuz bu klasör, arama yolları ekleyin.
- paketleri--hazırlama arasında iç klasörü yükler.
- bağlantı noktaları--Kataloğu, sürümü ve indirme nereden her kitaplıkta açıklamak dosyaları. Gerekirse, kendi bağlantı noktaları ekleyebilirsiniz.
- komut dosyaları--vcpkg tarafından kullanılan komut dosyaları (cmake, powershell).
- toolsrc--vcpkg ve ilgili bileşenler için C++ kaynak kodu
- triplets--her desteklenen hedef Platformu (örneğin, x86 windows veya x64 uwp) için ayarları içerir.

## <a name="command-line-reference"></a>Komut satırı başvurusu

|Komut|Açıklama|
|---------|---------|
|**vcpkg arama [pat]**|Paketleri yüklemek kullanılabilir arayın|
|**vcpkg yükleme \<pkg >...**|Paket yükleme|
|**vcpkg kaldırmak \<pkg >...**|Bir paketi kaldırma|
|**eski vcpkg Kaldır--**|Tüm güncel paketlerini kaldırma|
|**vcpkg list**|Yüklü listesinde paketleri|
|**vcpkg update**|Güncelleştirme paketleri listesini görüntüle|
|**vcpkg yükseltme**|Tüm güncel olmayan paketler yeniden oluşturma|
|**vcpkg karma \<dosyası > [algoritma]**|Belirli algoritması tarafından bir dosya karma, SHA512 varsayılan|
|**vcpkg tümleştirmek yükleme**|Yüklü yapma kullanıcı genelinde kullanılabilir paketler. İlk kullanımda yönetici ayrıcalıkları gerektirmez|
|**vcpkg tümleştirmek Kaldır**|Kullanıcı genelinde tümleşmesini kaldır|
|**vcpkg proje tümleştirme**|Tek başına VS proje kullanım başvuruda bulunan bir NuGet paketi oluştur|
|**vcpkg verme \<pkg >... [opt]...**|Bir paket verebilirsiniz|
|**vcpkg düzenleme \<pkg >**|(Kullanır Düzenleyicisi %, varsayılan 'code') düzenlemek için bir bağlantı noktasını açın|
|**vcpkg alma \<pkg >**|Önceden derlenmiş kitaplığı içeri aktarma|
|**vcpkg oluşturma \<pkg > \<URL'si > [archivename]**|Yeni bir paket oluşturun|
|**vcpkg sahibi \<pat >**|Yüklü paketler dosyalarında arayın|
|**vcpkg cache**|Paket listesi önbelleğe alınan derlenmiş|
|**vcpkg sürüm**|Sürüm bilgilerini görüntüle|
|**vcpkg contact**|Geri bildirim göndermek için kişi bilgilerini görüntüleme|

### <a name="options"></a>Seçenekler:
|Seçenek|Açıklama|
|---------|---------|
|**--Üçlü \<t >**|Hedef mimari Üçlü belirtin. (varsayılan: `%VCPKG_DEFAULT_TRIPLET%`, ayrıca bkz. **vcpkg Yardım Üçlü**)|
|**--vcpkg kök \<yolu >**|Vcpkg kök dizini belirtin (varsayılan: `%VCPKG_ROOT%`)|
