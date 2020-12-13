---
description: 'Daha fazla bilgi edinin: üçüncü taraf kitaplıkları taşıma'
title: Üçüncü taraf kitaplıklarını taşıma
ms.date: 10/29/2019
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
ms.openlocfilehash: cead058a6d3995a77726bc995996871eba29047f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331231"
---
# <a name="porting-third-party-libraries"></a>Üçüncü taraf kitaplıklarını taşıma

Visual Studio 2013 veya daha önceki bir projeyi Visual C++ güncel sürümüne yükselttiğinizde, projenin kullandığı tüm kitaplıkları da yükseltmeniz gerekir, böylece kitaplık ve projeniz derleyicinin aynı sürümü ve türü ile oluşturulur. Kitaplık kaynak koduna erişiminiz yoksa ve kitaplık vcpkg aracılığıyla kullanılamıyorsa, kitaplık satıcısından güncelleştirilmiş bir ikili edinmeniz gerekir. (Daha fazla bilgi için bkz. [olası yükseltme sorunlarına genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)).

Bir uygulamayı Visual Studio 2015 veya Visual Studio 2017 ' den Visual Studio 2019 ' ye yükseltirken, bu üç sürüm tarafından oluşturulan kod ikili uyumlu olduğundan bağımlılıkları yükseltmek gerekli değildir. Daha fazla bilgi için bkz. [Visual studio 2015 ve Visual studio 2019 arasındaki C++ ikili uyumluluğu](binary-compat-2015-2017.md).

## <a name="vcpkg-for-open-source-libraries"></a>açık kaynaklı kitaplıklar için vcpkg

Geçmişte, 3. taraf kitaplıklarını bulmak ve yükseltmek, bazen önemsiz olmayan bir görevdir. C++ üçüncü taraf açık kaynaklı kitaplıklarını edinmeyi ve yeniden oluşturmayı kolaylaştırmak için Visual C++ ekibi, **VC + + paketleme aracı** veya **vcpkg** adlı bir komut satırı aracı oluşturmuştur. Vcpkg 'da birçok popüler C++ açık kaynak kitaplığı ile aranabilir bir katalog bulunur. Katalogdan herhangi bir kitaplığı doğrudan vcpkg komut satırından yükleyebilirsiniz. Bir kitaplık yüklediğinizde, Vcpkg makinenizde bir dizin ağacı oluşturur ve bu klasöre. h,. lib ve ikilileri ekler. Bu klasörü, derleme komut satırınızla kullanabilir veya vcpkg tümleştir install komutunu kullanarak Visual Studio 2015 veya sonraki bir sürümü ile tümleştirebilirsiniz. Bir kitaplık konumunu tümleştirdikten sonra Visual Studio bunu bulup oluşturduğunuz yeni bir projeye ekleyebilir. Bir kitaplığı kullanmak için, yalnızca `#include` BT ve Visual Studio otomatik olarak. lib yolunu proje ayarlarınıza ekler ve DLL 'yi çözüm klasörünüze kopyalayacaktır. Daha fazla bilgi için bkz. [vcpkg: C++ için Paket Yöneticisi](../build/vcpkg.md).

## <a name="reporting-issues"></a>Raporlama sorunları

Açık kaynak kitaplığınız **vcpkg** kataloğunda mevcut değilse, [GitHub](https://github.com/Microsoft/vcpkg/issues) deposunda topluluğun ve Visual C++ ekibin onu görebileceği ve bu kitaplık için bağlantı noktası dosyasını oluşturabileceğiniz bir sorun açabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)
