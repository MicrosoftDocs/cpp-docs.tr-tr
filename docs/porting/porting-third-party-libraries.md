---
title: Üçüncü taraf kitaplıklarını taşıma | Microsoft Docs
ms.custom: ''
ms.date: 01/10/2017
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- 3rd-party libraries
- vspkg
ms.assetid: b055ed20-8a9e-45b2-ac2a-e3d94271c009
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e1edc9e4a6172b3ac55e7a8bc9b21cdc571774d
ms.sourcegitcommit: e9ce38decc9f986edab5543de3464b11ebccb123
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/13/2018
ms.locfileid: "42465363"
---
# <a name="porting-third-party-libraries"></a>Üçüncü taraf kitaplıklarını taşıma

Bir projeyi Visual C++'ın geçerli sürümüne yükselttiğinizde, aynı zamanda kitaplık ve projenize öğesinin aynı sürümünü ve derleyici örneğinizin yerleşiktir, böylece proje kullanan tüm kitaplıkları sürümüne yükseltmeniz gerekir. (Daha fazla bilgi için [olası yükseltme sorunlarına genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)). 

## <a name="introducing-vcpkg"></a>Vcpkg ile tanışın

Geçmişte, bulma ve 3. taraf kitaplıkları yükseltme bazen Önemsiz olmayan bir görev olmuştur. Almak ve C++'ı yeniden 3 kolaylaştırmak için taraf açık kaynak kitaplıkları, Visual C++ ekibine oluşturduğu adlı bir komut satırı aracı **VC ++ paketleme aracı** veya **vcpkg**. Vcpkg birçok popüler C++ açık kaynak kitaplıkları aranabilir kataloğunu sahiptir. Kitaplık Kataloğu vcpkg komut satırından doğrudan yükleyebilirsiniz. Bir kitaplık yükleme sırasında Vcpkg dizin ağacı makinenizde oluşturur ve ikili dosyaları bu klasörde ve .lib .h ekler. Bu klasör, derleme komut satırında kullanın veya Visual Studio 2015 ile tümleştirin veya daha sonra yükleme komutu vcpkg kullanarak tümleştirin. Bir kitaplık konumuna tümleştirdikten sonra Visual Studio bulmak ve oluşturduğunuz tüm yeni projeye ekleyin. Bir kitaplık kullanmak üzere yeni `#include` ve Visual Studio otomatik olarak proje ayarlarınızın .lib yolunu ekleyin ve dll, çözüm klasörüne kopyalayın. Daha fazla bilgi için [vcpkg: C++ için Paket Yöneticisi](../vcpkg.md).

## <a name="reporting-issues"></a>Raporlama konuları

Kitaplığınızı mevcut değilse **vcpkg** katalog, üzerinde bir sorunu açabilirsiniz [GitHub deposunu](https://github.com/Microsoft/vcpkg/issues) burada community ve Visual C++ ekibine görebilir ve büyük olasılıkla bu kitaplığa yönelik bağlantı noktası dosyasını oluşturun.

Özel için kitaplık sağlayıcı başvurmanızı öneririz 3 şahıs kitaplıklardaki (açık olmayan kaynak). Ancak, özel tüm kitaplıkların kullanıyorsanız ve engellediğiniz bilmeniz, bağlı olduğu hangisinin bize ilgilenen duyuyoruz (adresinden bize başvurun vcupgrade@microsoft.com).
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)