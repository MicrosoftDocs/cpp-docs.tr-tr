---
title: 'Nasıl Yapılır: Hedef Framework ve Platform Araç Kümesini Değiştirme'
ms.custom: conceptual
ms.date: 07/24/2019
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
ms.openlocfilehash: c5e7172fea06f6b455422fb023a0b6462b5c4103
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73964899"
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>Nasıl Yapılır: Hedef Framework ve Platform Araç Kümesini Değiştirme

Bir Visual Studio C++ proje dosyasını, C++ platform araç takımının farklı sürümlerini, Windows SDK ve .NET Framework (C++yalnızca/CLI projeleri) hedeflemek üzere düzenleyebilirsiniz. Varsayılan olarak, proje sistemi, projeyi oluşturmak için kullandığınız Visual Studio sürümüne karşılık gelen .NET Framework sürümünü ve araç kümesi sürümünü kullanır. Her derleme hedefi için aynı kod tabanını kullanabilmeniz için. vcxproj dosyasındaki tüm bu değerleri değiştirebilirsiniz.

## <a name="platform-toolset"></a>Platform araç takımı

Platform araç takımı, C/ C++ C++ standart kitaplıklarıyla birlikte derleyici (CL. exe) ve bağlayıcı (LINK. exe) ile oluşur. Visual Studio 2015 ' den itibaren, araç takımının ana sürümü 14 ' te kaldığı için, Visual Studio 2019 veya Visual Studio 2017 ile derlenen projelerin, Visual Studio 2015 ile derlenen projelerle ABı geriye dönük olarak uyumlu olduğu anlamına gelir. İkincil sürüm, Visual Studio 2015 ' den bu yana her sürüm için 1 ile güncelleştirilir:

- Visual Studio 2015: v140
- Visual Studio 2017: v141
- Visual Studio 2019: v142

Bu araç kümeleri .NET Framework 4,5 ve üstünü destekler.

Visual Studio, projeler için C++ Çoklu hedefleme da destekler. Visual Studio IDE 'yi kullanarak Visual Studio 'nun eski sürümleriyle oluşturulmuş projeleri düzenleme ve derleme, araç takımının yeni bir sürümünü kullanmak için yükseltme yapmadan kullanabilirsiniz. Bilgisayarınızda eski araç kümelerinin yüklü olması gerekir. Daha fazla bilgi için bkz. [Visual Studio 'da yerel çoklu](../porting/use-native-multi-targeting.md)sürüm desteği kullanımı. Örneğin, Visual Studio 2015 ' de .NET Framework 2,0 ' i *hedefleyebilir* , ancak bunu destekleyen önceki bir araç takımını kullanmanız gerekir.

## <a name="target-framework-ccli-project-only"></a>Hedef çerçeve (C++yalnızca/CLI Projesi)

Hedef Framework 'Ü değiştirdiğinizde, platform araç takımını da bu çerçeveyi destekleyen bir sürüm olarak değiştirin. Örneğin, .NET Framework 4,5 ' i hedeflemek için, Visual Studio 2015 (v140), Visual Studio 2013 (v120) veya Visual Studio 2012 (v110) gibi uyumlu bir platform araç takımını kullanmanız gerekir. .NET Framework 2,0, 3,0, 3,5 ve 4 ve x86/x64 platformlarını hedeflemek için [Windows 7,1 SDK](https://www.microsoft.com/download/details.aspx?id=8279) platformu araç takımını kullanabilirsiniz.

Özel bir platform araç takımı oluşturarak hedef platformu daha da genişletebilirsiniz. Daha fazla bilgi için C++ bkz [ C++ ](https://devblogs.microsoft.com/cppblog/c-native-multi-targeting/) . Visual blogda yerel çoklu sürüm desteği.

### <a name="to-change-the-target-framework"></a>Hedef Framework 'Ü değiştirmek için

1. Visual Studio 'da **Çözüm Gezgini**' de projenizi seçin. Menü çubuğunda, **Proje** menüsünü açın ve **Projeyi Kaldır**' ı seçin. Bu, projeniz için proje (. vcxproj) dosyasını kaldırır.

   > [!NOTE]
   >  Proje C++ dosyası Visual Studio 'da değiştirilirken bir proje yüklenemez. Ancak, proje Visual Studio 'ya yüklenirken proje dosyasını değiştirmek için Not Defteri gibi başka bir düzenleyiciyi de kullanabilirsiniz. Visual Studio, proje dosyasının değiştiğini algılar ve projeyi yeniden yüklemenizi ister.

1. Menü çubuğunda **Dosya**, **Aç**, **Dosya**' yı seçin. **Dosya Aç** iletişim kutusunda proje klasörünüze gidin ve proje (. vcxproj) dosyasını açın.

1. Proje dosyasında, hedef Framework sürümü için girişi bulun. Örneğin, projeniz 4,5 .NET Framework kullanmak üzere tasarlandıysa, `<Project>` öğesinin `<PropertyGroup Label="Globals">` öğesinde `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` bulun. `<TargetFrameworkVersion>` öğesi yoksa, projeniz .NET Framework kullanmaz ve değişiklik gerekli değildir.

1. Değeri, v 3.5 veya v 4.6 gibi istediğiniz Framework sürümü ile değiştirin.

1. Değişiklikleri kaydedin ve düzenleyiciyi kapatın.

1. **Çözüm Gezgini**' de, projeniz için kısayol menüsünü açın ve ardından **projeyi yeniden yükle**' yi seçin.

1. Değişikliği doğrulamak için, **Çözüm Gezgini**' de, projenizin kısayol menüsünü açmak için sağ tıklayın (çözümünüz için değil) ve ardından **Özellikler** ' i seçerek Proje **Özellik sayfaları** iletişim kutusunu açın. İletişim kutusunun sol bölmesinde **yapılandırma özellikleri** ' ni genişletin ve ardından **genel**' i seçin. **.Net hedef Framework sürümünün** yeni çerçeve sürümünü gösterdiğini doğrulayın.

### <a name="to-change-the-platform-toolset"></a>Platform araç takımını değiştirmek için

1. Visual Studio 'da, **Çözüm Gezgini**, projeniz için kısayol menüsünü açın (çözümünüz için değil) ve ardından **Özellikler** ' i seçerek Proje **Özellik sayfaları** iletişim kutusunu açın.

1. **Özellik sayfaları** iletişim kutusunda, **yapılandırma** açılan listesini açın ve ardından **tüm yapılandırmalar**' ı seçin.

1. İletişim kutusunun sol bölmesinde **yapılandırma özellikleri** ' ni genişletin ve ardından **genel**' i seçin.

1. Sağ bölmede **platform araç takımı** ' nı seçin ve ardından aşağı açılan listeden istediğiniz araç takımını seçin. Örneğin, Visual Studio 2010 araç takımını yüklediyseniz, projeniz için kullanmak üzere **Visual studio 2010 (v100)** öğesini seçin.

1. **Tamam** düğmesini seçin.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırında MSBuild-C++](msbuild-visual-cpp.md)
