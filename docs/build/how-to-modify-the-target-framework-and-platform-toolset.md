---
title: 'Nasıl yapılır: hedef Framework ve Platform araç kümesini değiştirme | Microsoft Docs'
ms.custom: conceptual
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.modifytargetframeworkandplatformtoolset
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: modify target framework and platform toolset'
ms.assetid: 031b1d54-e6e1-4da7-9868-3e75a87d9ffe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f21ec9d205e009438fac97914ec4b684713102a3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="how-to-modify-the-target-framework-and-platform-toolset"></a>Nasıl Yapılır: Hedef Framework ve Platform Araç Kümesini Değiştirme
Visual C++ proje ayarları .NET Framework'ün farklı sürümlerini hedefleyen ve farklı platform toolsets kullanacak şekilde değiştirebilirsiniz. Varsayılan olarak, .NET Framework sürümünü ve projeyi oluşturmak için kullandığınız Visual Studio sürümüne karşılık gelen araç takımının sürüm proje sistemi kullanır. Hedef platform araç takımı, proje özelliklerini değiştirerek değiştirebilirsiniz. Hedef Framework projesi (.vcxproj) dosyasını değiştirerek değiştirebilirsiniz. Ayrı bir kod her derleme hedefi için temel sağlamak zorunda değildir.  
  
> [!IMPORTANT]
>  Bazı sürümlerinde değiştirilmiş hedef çerçeveyi veya platform toolsets desteklemeyebilir. Uyumluluk bilgileri için bkz: [bağlantı noktası, geçirme ve yükseltme Visual Studio projeleri](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects).  
  
 Ayrıca hedef Framework değiştirdiğinizde, platform araç takımı, Framework destekleyen bir sürüm olarak değiştirin. Örneğin, .NET Framework 4.5 hedeflemek için Visual Studio 2015 (v140), Visual Studio 2013 (v120) veya Visual Studio 2012 (v110) gibi bir uyumlu platform araç takımı kullanmanız gerekir. Kullanabileceğiniz **Windows7.1SDK** .NET Framework 2.0, 3.0, 3.5 ve 4 ve Itanium, x86 hedeflemek için platform araç takımı ve x64 platformlar.  
  
> [!NOTE]
>  Hedef platform araç takımı değiştirmek için ilgili sürümü Visual Studio ya da Windows Platform SDK yüklü olması gerekir. Örneğin, Itanium platformuyla hedeflemek için **Windows7.1SDK** platform araç takımı, olmalıdır [Windows 7 için Microsoft Windows SDK ve .NET Framework 4 SP1](http://www.microsoft.com/download/details.aspx?id=8279) yüklü; ancak, kullanabilirsiniz Visual Studio geliştirme işinizi doğru Framework sürümü ve platform araç takımı hedef koşuluyla yapmak için başka bir uyumlu sürümü.  
  
 Daha fazla hedef platformu özel platform araç takımı oluşturarak genişletebilirsiniz. Daha fazla bilgi için bkz: [C++ yerel çoklu sürüm desteği](http://go.microsoft.com/fwlink/p/?linkid=196619) Visual C++ blogunda.  
  
### <a name="to-change-the-target-framework"></a>Hedef Framework değiştirmek için  
  
1.  Visual Studio içinde **Çözüm Gezgini**, projenizi seçin. Menü çubuğunda açmak **proje** menü ve **projeyi**. Projeniz için proje (.vcxproj) dosyası kaldırır.  
  
    > [!NOTE]
    >  Visual Studio Proje dosyası değiştirilirken C++ projesi yüklenemiyor. Ancak, Visual Studio Proje yüklenirken proje dosyasını değiştirmek için Not Defteri gibi başka bir Düzenleyicisi kullanabilirsiniz. Visual Studio Proje dosyası değişti ve projeyi yeniden yüklemek ister algılar.  
  
2.  Menü çubuğunda seçin **dosya**, **açık**, **dosya**. İçinde **Dosya Aç** iletişim kutusunda, proje klasörüne gidin ve proje (.vcxproj) dosyasını açın.  
  
3.  Proje dosyasında hedef Framework sürümü girişini bulun. Projeniz .NET Framework 4.5 kullanmak üzere tasarlanmış, örneğin, bulun `<TargetFrameworkVersion>v4.5</TargetFrameworkVersion>` içinde `<PropertyGroup Label="Globals">` öğesinin `<Project>` öğesi. Varsa `<TargetFrameworkVersion>` öğesi mevcut değilse, projeniz .NET Framework kullanmayan ve hiçbir değişiklik gereklidir.  
  
4.  Değeri, v3.5 veya v4.6 gibi istediğiniz Framework sürüm olarak değiştirin.  
  
5.  Değişiklikleri kaydetmek ve Düzenleyicisi'ni kapatın.  
  
6.  İçinde **Çözüm Gezgini**, projeniz için kısayol menüsünü açın ve ardından **projeyi yeniden yükle**.  
  
7.  Değişikliği doğrulamak için **Çözüm Gezgini**, projenizin (değil, çözümünüz için) için kısayol menüsünü açın ve ardından sağ **özellikleri** projenizi açmak için **özelliği Sayfaları** iletişim kutusu. İletişim kutusunun sol bölmesinde, **yapılandırma özellikleri** ve ardından **genel**. Doğrulayın **.NET hedef Framework sürümü** yeni Framework sürümünü gösterir.  
  
### <a name="to-change-the-project-toolset"></a>Proje araç takımı değiştirmek için  
  
1.  Visual Studio içinde **Çözüm Gezgini**, projenizin (değil, çözümünüz için) için kısayol menüsünü açın ve ardından **özellikleri** projenizi açmak için **özellik sayfaları**iletişim kutusu.  
  
2.  İçinde **özellik sayfaları** açık iletişim kutusunu **yapılandırma** aşağı açılan listeyi ve ardından **tüm yapılandırmaları**.  
  
3.  İletişim kutusunun sol bölmesinde, **yapılandırma özellikleri** ve ardından **genel**.  
  
4.  Sağ bölmede seçin **Platform araç takımı** ve ardından istediğiniz araç takımı aşağı açılan listeden seçin. Örneğin, yüklediyseniz [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)] araç takımı, select **Visual Studio 2010 (nı v100)** projeniz için kullanılacak.  
  
5.  Seçin **Tamam** düğmesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)