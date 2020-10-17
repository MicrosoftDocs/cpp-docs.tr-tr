---
title: 'Nasıl Yapılır: Özel Araçlarla Proje Özelliklerini Tümleştirme'
description: Özel araçları Visual Studio C++ projelerindeki proje özellikleriyle tümleştirme.
ms.date: 10/08/2020
helpviewer_keywords:
- 'MSBuild (C++), howto: integrate custom tools'
ms.openlocfilehash: 4b88bf94a92efaf5046fd83e5c6358f3fdf80895
ms.sourcegitcommit: 6e5429e076e552b32e8bdc49480c51498d7924c1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2020
ms.locfileid: "92099673"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Nasıl Yapılır: Özel Araçlarla Proje Özelliklerini Tümleştirme

XML dosyası oluşturarak Visual Studio **Özellik sayfaları** penceresine özel araç seçenekleri ekleyebilirsiniz.

**Özellik sayfaları** penceresinin **yapılandırma özellikleri** bölümü, *kural*olarak bilinen ayar gruplarını görüntüler. Her kural bir araç veya bir özellik grubu için ayarları içerir. Örneğin, **bağlayıcı** kuralı bağlayıcı aracının ayarlarını içerir. Kuraldaki ayarlar alt *kategorilere*ayrılabilir.

Visual Studio başlatıldığında özelliklerin yüklenebilmesi için özel aracınızın özelliklerini içeren bir kural dosyası oluşturabilirsiniz. Dosyanın nasıl değiştirileceği hakkında bilgi için bkz. Visual Studio proje ekibi blogu üzerinde [Platform genişletilebilirliği Bölüm 2](/archive/blogs/vsproject/platform-extensibility-part-2) .

::: moniker range="vs-2015"

Kural dosyanızı yerleştireceğiniz klasör, yerel ayara ve kullanımda olan Visual Studio sürümüne bağlıdır. Visual Studio 2015 veya önceki bir geliştirici komut isteminde Rules klasörü *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>`* . `<version>`Değer *`v140`* Visual Studio 2015 ' dir. , `<locale>` Örneğin, İngilizce için BIR LCID 'dir `1033` . Visual Studio 'nun yüklü her sürümü için ve her dil için farklı bir yol kullanacaksınız. Örneğin, Ingilizce 'de Visual Studio 2015 Community Edition için varsayılan kurallar klasör yolu olabilir *`C:\Program Files (x86)\MSBuild\Microsoft.Cpp\v4.0\v140\1033\`* .

::: moniker-end

::: moniker range="vs-2017"

Kural dosyanızı yerleştireceğiniz klasör, yerel ayara ve kullanımda olan Visual Studio sürümüne bağlıdır. Visual Studio 2017 Geliştirici komut isteminde Rules klasörü *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . , `<locale>` Örneğin, İngilizce için BIR LCID 'dir `1033` . Visual Studio 2015 veya önceki bir geliştirici komut isteminde, Rules klasörü, *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* burada `<version>` değer *`v140`* Visual Studio 2015 ' dir. Visual Studio 'nun yüklü her sürümü için ve her dil için farklı bir yol kullanacaksınız. Örneğin, Ingilizce 'de Visual Studio 2017 Community Edition için varsayılan kurallar klasör yolu olabilir *`C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033\`* .

::: moniker-end

::: moniker range=">=vs-2019"

Kural dosyanızı yerleştireceğiniz klasör, yerel ayara ve kullanımda olan Visual Studio sürümüne bağlıdır. Visual Studio 2019 veya sonraki bir geliştirici komut isteminde, Rules klasörü, *`%VSINSTALLDIR%MSBuild\Microsoft\VC\<version>\<locale>\`* burada `<version>` değer *`v160`* Visual Studio 2019 ' dir. , `<locale>` Örneğin, İngilizce için BIR LCID 'dir `1033` . Visual Studio 2017 ' de, Rules klasörü *`%VSINSTALLDIR%Common7\IDE\VC\VCTargets\<locale>\`* . Visual Studio 2015 veya önceki bir geliştirici komut isteminde Rules klasörü *`%ProgramFiles(x86)%\MSBuild\Microsoft.Cpp\v4.0\<version>\<locale>\`* . Visual Studio 'nun yüklü her sürümü için ve her dil için farklı bir yol kullanacaksınız. Örneğin, Ingilizce 'de Visual Studio 2019 Community Edition için varsayılan kurallar klasör yolu olabilir *`C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Microsoft\VC\v160\1033\`* .

::: moniker-end

### <a name="to-add-or-change-project-properties"></a>Proje özellikleri eklemek veya değiştirmek için

1. XML düzenleyicisinde bir XML dosyası oluşturun.

1. Dosyayı varsayılan kurallar klasörüne kaydedin. Diliniz ve Visual Studio sürümünüz için yolu ayarlayın. **Özellik sayfaları** penceresindeki her kural, bu KLASÖRDEKI bir XML dosyası tarafından temsil edilir. Dosyanın klasörde benzersiz olarak adlandırıldığından emin olun.

1. Gibi var olan bir kural dosyasının içeriğini kopyalayın, *`rc.xml`* değişiklikleri kaydetmeden kapatın ve sonra içeriği yenı XML dosyanıza yapıştırın. Şablon olarak kullanmak üzere herhangi bir XML şema dosyasını kopyalayabilirsiniz. Aracınızın benzerine benzer bir tane seçin.

1. Yeni XML dosyasında, içeriği gereksinimlerinize göre değiştirin. Dosyanın en üstündeki **kural adı** ve **kural. DisplayName** ' i değiştirdiğinizden emin olun.

1. Değişikliklerinizi kaydedin ve dosyayı kapatın.

1. Kurallar klasöründeki XML dosyaları, Visual Studio başladığında yüklenir. Yeni dosyayı test etmek için Visual Studio 'Yu yeniden başlatın.

1. **Çözüm Gezgini**, bir projeye sağ tıklayın ve ardından **Özellikler**' i seçin. **Özellik sayfaları** penceresinde, kuralınız adına sahip yeni bir düğüm olduğunu doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırında MSBuild-C++](msbuild-visual-cpp.md)
