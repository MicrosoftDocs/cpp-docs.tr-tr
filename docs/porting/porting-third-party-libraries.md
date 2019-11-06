---
title: Üçüncü taraf kitaplıklarını taşıma
ms.date: 10/29/2019
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
ms.openlocfilehash: 89460af1ad0b356f4f5952141636a9f067131750
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627186"
---
# <a name="porting-third-party-libraries"></a>Üçüncü taraf kitaplıklarını taşıma

Bir projeyi Visual Studio 2013 veya daha önceki bir sürüme güncel görsele C++yükselttiğinizde, kitaplığın ve projenizin aynı derleme sürümü ve türü ile oluşturulması için projenin kullandığı tüm kitaplıkları da yükseltmeniz gerekir. Kitaplık kaynak koduna erişiminiz yoksa ve kitaplık vcpkg aracılığıyla kullanılamıyorsa, kitaplık satıcısından güncelleştirilmiş bir ikili edinmeniz gerekir. (Daha fazla bilgi için bkz. [olası yükseltme sorunlarına genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)).

Bir uygulamayı Visual Studio 2015 veya Visual Studio 2017 ' den Visual Studio 2019 ' ye yükseltirken, bu üç sürüm tarafından oluşturulan kod ikili uyumlu olduğundan bağımlılıkları yükseltmek gerekli değildir. Daha fazla bilgi için bkz [ C++ . Visual Studio 2015 ve Visual Studio 2019 arasında ikili uyumluluk](binary-compat-2015-2017.md).

## <a name="vcpkg-for-open-source-libraries"></a>açık kaynaklı kitaplıklar için vcpkg

Geçmişte, 3. taraf kitaplıklarını bulmak ve yükseltmek, bazen önemsiz olmayan bir görevdir. C++ Visual C++ ekibi, üçüncü taraf açık kaynak kitaplıklarını edinmeyi ve yeniden oluşturmayı kolaylaştırmak için, **VC + + paketleme aracı** veya **vcpkg**adlı bir komut satırı aracı oluşturmuştur. Vcpkg, birçok popüler C++ açık kaynak kitaplığı ile aranabilir bir kataloğa sahiptir. Katalogdan herhangi bir kitaplığı doğrudan vcpkg komut satırından yükleyebilirsiniz. Bir kitaplık yüklediğinizde, Vcpkg makinenizde bir dizin ağacı oluşturur ve bu klasöre. h,. lib ve ikilileri ekler. Bu klasörü, derleme komut satırınızla kullanabilir veya vcpkg tümleştir install komutunu kullanarak Visual Studio 2015 veya sonraki bir sürümü ile tümleştirebilirsiniz. Bir kitaplık konumunu tümleştirdikten sonra Visual Studio bunu bulup oluşturduğunuz yeni bir projeye ekleyebilir. Bir kitaplığı kullanmak için, yalnızca `#include` ve Visual Studio otomatik olarak. lib yolunu proje ayarlarınıza ekler ve DLL 'yi çözüm klasörünüze kopyalayacaktır. Daha fazla bilgi için bkz. [vcpkg: Için C++bir paket yöneticisi ](../build/vcpkg.md).

## <a name="reporting-issues"></a>Raporlama sorunları

Açık kaynak kitaplığınız **vcpkg** kataloğunda yoksa, bir [GitHub](https://github.com/Microsoft/vcpkg/issues) deposunda topluluk ve görsel C++ ekibin onu görebileceği ve bu kitaplık için bağlantı noktası dosyasını oluşturabileceğiniz bir sorun açabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)
