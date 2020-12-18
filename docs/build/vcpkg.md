---
title: 'vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi'
description: vcpkg, Windows, macOS ve Linux 'ta açık kaynaklı C++ kitaplıklarının alımı ve yüklemesini büyük ölçüde kolaylaştıran bir komut satırı paket yöneticisidir.
ms.custom: contperf-fy21q2
ms.date: 12/11/2020
ms.topic: overview
ms.technology: cpp-ide
ms.openlocfilehash: f937f1df718bf8dfcc0ae5166d8b9eb671d2d8ab
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97682472"
---
# <a name="vcpkg-a-c-package-manager-for-windows-linux-and-macos"></a>vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi

vcpkg, C ve C++ kitaplıkları için platformlar arası bir komut satırı paket yöneticisidir. Windows, Linux ve macOS 'ta üçüncü taraf kitaplıkların alımı ve yüklenmesini basitleştirir. Projeniz üçüncü taraf kitaplıklar kullanıyorsa, bunları yüklemek için vcpkg kullanmanızı öneririz. vcpkg hem açık kaynaklı hem de özel kitaplıkları destekler. Vcpkg Windows kataloğundaki tüm kitaplıklar, Visual Studio 2015, Visual Studio 2017 ve Visual Studio 2019 uyumluluğu için test edilmiştir. Windows ve Linux/macOS katalogları arasında vcpkg artık binlerce kitaplığı desteklemektedir. C++ topluluğu, her iki katalogda de sürekli olarak daha fazla kitaplık ekler.

## <a name="how-to-get-and-use-vcpkg"></a>Vcpkg alma ve kullanma

GitHub deposundan Yerel bir kopya yaparak vcpkg 'yi yükler [https://github.com/Microsoft/vcpkg](https://github.com/Microsoft/vcpkg) . Ardından, vcpkg-Bootstrapper betiğini çalıştırarak ayarlayın. Ayrıntılı yükleme yönergeleri için bkz. [vcpkg 'Yi yükleme](install-vcpkg.md). Vcpkg 'yi Visual Studio veya Visual Studio Code geliştirme ortamıyla tümleştirmek için bkz. [tümleştirme vcpkg](integrate-vcpkg.md). Ardından, vcpkg 'yi kullanarak bir kitaplığı yüklemeyi veya güncelleştirmeyi, bkz. [kitaplıkları vcpkg Ile yönetme](manage-libraries-with-vcpkg.md). Vcpkg komutları hakkında daha fazla bilgi için bkz. [vcpkg komut satırı başvurusu](vcpkg-command-line-reference.md).

## <a name="how-vcpkg-works"></a>Vcpkg nasıl kullanılır?

Vcpkg projesi, GitHub 'da bulunan açık kaynaklı kaynaktır. Vcpkg deposunun bir *kopyası* veya yerel kopyası vcpkg yürütülebilir dosyasını ve *kataloğunu*, bir kitaplığı ve seçeneklerini tanımlayan paketlerin bir listesini içerir. Her pakette, bir veya daha fazla *bağlantı noktası*, kaynaklardan kitaplık alma ve derleme ile ilgili bilgiler veya belirli bir hedef ortam için ikili bir sürüm indirilir. Bir kitaplık yüklemek için vcpkg kullandığınızda, bir kitaplığı indirmek ve kullanmak için, vcpkg dizininin bir alt dizininde kitaplığın yerel bir kopyasını oluşturmak için paket ve bağlantı noktası bilgilerini kullanır.

Kaynak biçiminde bir kitaplık kullanılabilir olduğunda vcpkg, ikili dosyalar yerine kaynakları indirir. Bu kaynakları, C veya C++ derleyicisinin en son sürümünü ve bulabileceği araçları kullanarak derler. C++ ABı uyumluluğu için hem uygulama kodunuzun hem de kullandığınız kitaplıkların aynı derleyicinin aynı sürümü tarafından derlenmesi önemlidir. Vcpkg kullanarak, eşleşmeyen ikili dosyalar ve neden olabilecek sorunlar için potansiyelini ortadan kaldırır veya en azından büyük ölçüde azaltabilirsiniz. Bir derleyicinin belirli bir sürümünde standartlaştırın ekiplerinde, bir takım üyesi kaynakları indirmek ve bir ikili dosya derlemek için vcpkg kullanabilir. Bir ekibin ortak kitaplıklarını indirmesi ve derlemesi için herkese açık hale getirmek verimsiz olur. Bir ekip üyesi, **`vcpkg export`** ikili dosyaları ve üstbilgileri veya bir NuGet paketini ortak bir ZIP dosyası oluşturmak için komutunu kullanabilir. Daha sonra, diğer ekip üyeleriyle kolayca paylaşabilirsiniz.

## <a name="customize-vcpkg-instances-for-different-targets"></a>Farklı hedefler için vcpkg örneklerini özelleştirme

Makinenizde vcpkg 'nin birden çok kopyasını veya *örneğini* kopyalayabilir ve her birini belirli amaçlarla özelleştirebilirsiniz. Her örnekte, farklı kitaplıklar yükleyebilir, hatta kütüphanelerin ortak katalogda bulunanlara farklı sürümleri yükleyebilirsiniz. Her örnek, tercih ettiğiniz derleyici seçeneklerini kullanarak özel bir kitaplık koleksiyonu oluşturmak üzere ayarlanabilir. Her örnek, yalnızca kendi hiyerarşisinde çalışan vcpkg.exe kendi kopyasının bulunduğu kendi kendine dahil olan bir ortamdır. vcpkg herhangi bir ortam değişkenine eklenmez ve Windows kayıt defteri veya Visual Studio 'ya bağımlılığı yoktur.

Ayrıca, bağlantı noktaları koleksiyonunda özel kitaplıkları olan bir vcpkg kopyası da oluşturabilirsiniz. Önceden oluşturulmuş ikili dosyalarınızı ve üst bilgilerinizi indiren bir bağlantı noktası ekleyebilirsiniz. Ardından, bu dosyaları yalnızca tercih edilen konuma kopyalayan bir *portfile. CMake* dosyası yazın.

## <a name="the-vcpkg-folder-hierarchy"></a>Vcpkg klasör hiyerarşisi

Tüm vcpkg işlevleri ve verileri, örnek başına tek bir Dizin hiyerarşisinde bulunur. Kayıt defteri ayarları veya ortam değişkeni yok. Bir makine üzerinde herhangi bir sayıda vcpkg örneğine sahip olabilirsiniz ve birbirini engellemez.

Vcpkg örneğinin içeriği şunlardır:

- *`buildtrees`* -Her kitaplığın oluşturulduğu kaynak alt klasörlerini içerir.
- *`docs`* -belgeler ve örnekler.
- *`downloads`* -İndirilen araçların veya kaynakların önbelleğe alınmış kopyaları. vcpkg, Install komutunu çalıştırdığınızda önce burada arama yapar.
- *`installed`* -Yüklü her kitaplığın üst bilgilerini ve ikili dosyalarını içerir. Visual Studio ile tümleştirdiğinizde, temelde bu klasörü arama yollarına eklemesini söylemiş olursunuz.
- *`packages`* -Yüklemeler arasında hazırlama için iç klasör.
- *`ports`* -Katalogdaki her kitaplığı, sürümünü ve nereden indirileceği dosyaları. Gerekirse, kendi bağlantı noktalarınızı ekleyebilirsiniz.
- *`scripts`* -Vcpkg tarafından kullanılan betikler (CMake, PowerShell).
- *`toolsrc`* -Vcpkg ve ilgili bileşenler için C++ kaynak kodu.
- *`triplets`* -Desteklenen her bir hedef platformun (örneğin, x86-Windows veya x64-UWP) ayarlarını içerir.

## <a name="telemetry"></a>Telemetri

vcpkg, deneyiminizi iyileştirmemize yardımcı olmak için kullanım verilerini toplar. Microsoft tarafından toplanan veriler anonimdir. **`bootstrap-vcpkg.bat`** Seçeneğini kullanarak veya betiğini yeniden çalıştırarak Telemetriyi devre dışı bırakabilirsiniz **`bootstrap-vcpkg.sh`** **`-disableMetrics`** . Ya da seçeneği, **`--disable-metrics`** komut satırında vcpkg ' ye geçirin. Ayrıca, ortam değişkenini ayarlayarak ölçümleri devre dışı bırakabilirsiniz `VCPKG_DISABLE_METRICS` .

## <a name="send-feedback-about-vcpkg"></a>Vcpkg hakkında geri bildirim gönderin

**`vcpkg contact --survey`** Hata raporları ve özellikler için öneriler de dahil olmak üzere Microsoft 'a vcpkg hakkında geri bildirim göndermek için komutunu kullanın. Daha fazla bilgi için bkz. [vcpkg komut satırı başvurusu](vcpkg-command-line-reference.md).

## <a name="see-also"></a>Ayrıca bkz.

[GitHub üzerinde vcpkg](https://github.com/Microsoft/vcpkg)\
[Vcpkg 'yi yükler](install-vcpkg.md)\
[Vcpkg 'yi tümleştirin](integrate-vcpkg.md)\
[Vcpkg ile kitaplıkları yönetme](manage-libraries-with-vcpkg.md)\
[vcpkg komut satırı başvurusu](vcpkg-command-line-reference.md)\
[Hızlı başlangıç](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Sık sorulan sorular](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
