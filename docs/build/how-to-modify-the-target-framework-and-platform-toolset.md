---
title: 'Nasıl yapılır: Hedef Framework ve Platform araç kümesini değiştirme'
ms.custom: conceptual
ms.date: 05/06/2019
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
ms.openlocfilehash: b2cf5ac5c6a339917b87a25001be568a7caa2247
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450744"
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>Nasıl yapılır: Hedef Framework ve Platform araç kümesini değiştirme

Visual Studio değiştirebilirsiniz C++ proje .NET Framework'ün farklı sürümlerini hedefleyen ve farklı platform araç takımları kullanacak şekilde ayarlar. Varsayılan olarak, proje sistemi .NET Framework sürümünü ve projeyi oluşturmak için kullandığınız Visual Studio sürümüne karşılık gelen araç kümesi sürümünü kullanır. Proje özelliklerini değiştirerek hedef platform araç takımını değiştirebilirsiniz. Proje (.vcxproj) dosyasını değiştirerek hedef Framework'ü değiştirebilirsiniz. Ayrı bir kod tabanı her derleme hedefi korumak zorunda değildir.

> [!IMPORTANT]
>  Bazı sürümler değiştirilmiş hedef Framework'leri veya platform araç takımlarını desteklemiyor olabilir. Uyumluluk bilgileri için bkz. [bağlantı noktası, geçirme ve yükseltme Visual Studio projeleri](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects).

Ayrıca, hedef Framework'ü değiştirdiğinizde, platform araç takımını, Framework destekleyen bir sürüm olarak değiştirin. Örneğin, .NET Framework 4.5 hedeflemek için Visual Studio 2015 (v140), Visual Studio 2013 (v120) veya Visual Studio 2012 (v110) gibi uyumlu bir platform araç takımını kullanmanız gerekir. Kullanabileceğiniz **Windows7.1SDK** .NET Framework 2.0, 3.0, 3.5 ve 4 ve x86, Itanium, hedef platform araç setini ve x64 platformlar.

> [!NOTE]
>  Hedef platform araç takımını değiştirmek için Visual Studio veya Windows Platform SDK ilişkili sürümü olması gerekir. Örneğin, Itanium platformunu hedeflemek için **Windows7.1SDK** platform araç olmalıdır [Windows 7 için Microsoft Windows SDK ve .NET Framework 4 SP1](https://www.microsoft.com/download/details.aspx?id=8279) yüklü; ancak kullanabilirsiniz doğru Framework sürümünü ve platform araç kümesini hedeflemek koşuluyla geliştirme çalışmalarınızı yapmak için Visual Studio'nun uyumlu başka bir sürümü.

Özel platform araç takımı oluşturarak hedef platformu genişletebilirsiniz. Daha fazla bilgi için [yerel C++ çoklu sürüm desteğinin](https://blogs.msdn.microsoft.com/vcblog/2009/12/08/c-native-multi-targeting/) Visual C++ blogundaki.

### <a name="to-change-the-target-framework"></a>Hedef Framework'ü değiştirmek için

1. Visual Studio içinde **Çözüm Gezgini**, projenizi seçin. Menü çubuğunda açın **proje** menüsünü seçip **projeyi**. Bu, projeniz için proje (.vcxproj) dosyasını kaldırır.

    > [!NOTE]
    >  Bir C++ projesi, proje dosyası Visual Studio içinde değiştirilirken yüklenemez. Ancak, proje Visual Studio'ya yüklendiğinde proje dosyasını değiştirmek için Not Defteri gibi bir düzenleyici kullanabilirsiniz. Visual Studio, proje dosyası değiştirildi ve projeyi yeniden yüklemenizi ister algılar.

1. Menü çubuğunda, seçin **dosya**, **açık**, **dosya**. İçinde **Dosya Aç** iletişim kutusunda proje klasörüne gidin ve ardından Proje (.vcxproj) dosyasını açın.

1. Proje dosyasında hedef Framework sürümü girişini bulun. Örneğin, projeniz .NET Framework 4.5 kullanmak üzere tasarlanmışsa, bulun `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` içinde `<PropertyGroup Label="Globals">` öğesinin `<Project>` öğesi. Varsa `<TargetFrameworkVersion>` öğesi hazır değilse projeniz .NET Framework'ü kullanmaz ve değişiklik gerekli değil.

1. V3.5 veya v4.6 gibi istediğiniz Framework sürümüne değerini değiştirin.

1. Değişiklikleri kaydedin ve düzenleyiciyi kapatın.

1. İçinde **Çözüm Gezgini**, projeniz için kısayol menüsünü açın ve ardından **projeyi**.

1. Değişikliği doğrulamak için **Çözüm Gezgini**, (için değil, çözümünüzün), projeniz için kısayol menüsünü açın ve ardından sağ tıklama **özellikleri** projenizi **özelliği Sayfaları** iletişim kutusu. İletişim kutusunun sol bölmesinde **yapılandırma özellikleri** seçip **genel**. Doğrulayın **.NET hedef Framework sürümü** alanında yeni Framework sürümünün gösterir.

### <a name="to-change-the-project-toolset"></a>Proje araç takımını değiştirmek için

1. Visual Studio içinde **Çözüm Gezgini**, (için değil, çözümünüzün), projeniz için kısayol menüsünü açın ve ardından **özellikleri** projenizi **özellik sayfaları**iletişim kutusu.

1. İçinde **özellik sayfaları** açık iletişim kutusunu **yapılandırma** aşağı açılan liste ve ardından **yapılandırmalarında**.

1. İletişim kutusunun sol bölmesinde **yapılandırma özellikleri** seçip **genel**.

1. Sağ bölmede seçin **Platform araç takımını** ve ardından açılır listeden istediğiniz araç setini'ı seçin. Örneğin, Visual Studio 2010 araç takımı yüklediyseniz seçin **Visual Studio 2010 (v100)** projeniz için kullanılacak.

1. Seçin **Tamam** düğmesi.

## <a name="see-also"></a>Ayrıca bkz.

[MSBuild komut satırında - C++](msbuild-visual-cpp.md)
