---
title: Üçüncü taraf kitaplıklar taşıma | Microsoft Docs
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
ms.openlocfilehash: 0e831f5441d62a4430fe036be70f1bec5ac99c98
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33849723"
---
# <a name="porting-third-party-libraries"></a>Üçüncü taraf kitaplıklar bağlantı noktası oluşturma

Bir projesini Visual C++ geçerli sürüme yükselttiğinizde, ayrıca kitaplığı ve projenizin aynı sürümü ve derleyici örneğinizin yerleşik böylece proje kullanan tüm kitaplıkları yükseltmeniz gerekir. (Daha fazla bilgi için bkz: [olası yükseltme sorunlarını genel bakış](overview-of-potential-upgrade-issues-visual-cpp.md)). 

## <a name="introducing-vcpkg"></a>Vcpkg Tanıtımı
Geçmişte, bulma ve 3 taraf kitaplıklar yükseltme bazen Önemsiz olmayan bir görev olmuştur. Edinmeli ve C++ yeniden 3 kolaylaştırmak için taraf açık kaynak kitaplıkları, Visual C++ ekip oluşturdu adlı bir komut satırı aracı **VC ++ paketleme aracı** veya **vcpkg**. Vcpkg birçok popüler C++ açık kaynak kitaplıkları aranabilir kataloğunu sahiptir. Tüm kitaplık kataloğu doğrudan vcpkg komut satırından yükleyebilirsiniz. Bir kitaplığı yüklediğinizde Vcpkg makinenizde bir dizin ağacında oluşturur ve ikili dosyaları bu klasörde ve .lib .h ekler. Derleme komut satırında, bu klasörü kullanın veya Visual Studio 2015 tümleştirmek veya daha sonra vcpkg kullanarak yükleme komut tümleştirin. Bir kitaplık konumu tümleştirdiğinizde, Visual Studio bulmak ve oluşturduğunuz tüm yeni projeye ekleyin. Sadece bir kitaplık kullanmak için #include ve Visual Studio otomatik olarak proje ayarlarınızı .lib yolu ekleyin ve dll çözüm klasörünüze kopyalayın. Daha fazla bilgi için bkz: [vcpkg: C++ için bir paket Yöneticisi](../vcpkg.md).


## <a name="reporting-issues"></a>Raporlama konuları
Kitaplığınızı vcpkg Kataloğu'nda mevcut değilse, üzerinde bir sorun açabilirsiniz [GitHub deposuna](https://github.com/Microsoft/vcpkg/issues) burada topluluk ve Visual C++ ekip onu görebilir ve büyük olasılıkla bu kitaplık için bağlantı noktası dosyası oluşturun.

Özel için öneririz kitaplık sağlayıcısına başvurun 3 taraf kitaplıkları (açık olmayan kaynak). Ancak, biz herhangi özel kitaplıklar kullanmakta olduğunuz ve engellediğiniz bilmeniz, size bağlıdır hangisinin bize bildirin ilgilendiğiniz (adresinden bize başvurun vcupgrade@microsoft.com).

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Taşıma ve Yükseltme Kılavuzu](visual-cpp-porting-and-upgrading-guide.md)
