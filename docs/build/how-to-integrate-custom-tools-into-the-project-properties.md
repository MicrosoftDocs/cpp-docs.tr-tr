---
title: 'Nasıl yapılır: özel araçlarla proje özelliklerini tümleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 04/27/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- msbuild.cpp.howto.integratecustomtools
dev_langs:
- C++
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 047427c344e8768fafa984ac72984c968d60238f
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693847"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Nasıl Yapılır: Özel Araçlarla Proje Özelliklerini Tümleştirme
Visual Studio için özel araç seçenekleri ekleyebilirsiniz **özellik sayfaları** arka plandaki XML şema dosyası oluşturarak penceresi.  
  
 **Yapılandırma özellikleri** bölümünü **özellik sayfaları** pencere görüntüler olarak bilinen bir ayar grupları *kuralları*. Her kural için bir aracı veya bir Grup ayarlarını içerir. Örneğin, **bağlayıcı** kural bağlayıcı aracı ayarlarını içerir. Bir kural ayarlarında içine alt *kategorileri*.  
  
 Bu belgede, özel aracınızı özellikleri içerir ve böylece Visual Studio başladığında özellikleri yüklü bir kümesi dizindeki bir dosya oluşturmak açıklanmaktadır. Dosya değiştirme hakkında daha fazla bilgi için bkz: [Platform Extensibilty Kısım 2](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/) Visual Studio Proje Ekibi blogunda.  
  
### <a name="to-add-or-change-project-properties"></a>Proje özellik eklemek veya değiştirmek için  
  
1.  XML Düzenleyicisi'nde bir XML dosyası oluşturun.  
  
2.  Visual Studio 2017'de dosyayı kaydetmek `VCTargets\1033` klasör. Her sürümün yüklü Visual Studio 2017'in ve her dil için farklı bir yol gerekir. Örneğin, Visual Studio Enterprise sürümünde İngilizce için klasör yolu olan `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Dil ve Visual Studio sürüm yolunu ayarlayın. Her kuralda **özellik sayfaları** penceresi bu klasördeki bir XML dosyası ile temsil edilir. Dosyayı klasörde benzersiz şekilde adlandırılmıştır emin olun.  
  
3.  İçeriğini kopyalayın `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`değişiklikleri kaydetmeden kapatın ve içeriği yeni XML dosyanıza yapıştırın. Herhangi bir XML şema dosyası kullanabilirsiniz - tek bir şablonla başlamak için kullanılabilecek budur.  
  
4.  Yeni XML dosyasında içerik gereksinimlerinize göre değiştirin. Değiştirdiğinizden emin olun **kural adı** ve **Rule.DisplayName** dosyanın üst.  
  
5.  Değişiklikleri kaydedin ve dosyayı kapatın.  
  
6.  XML dosyaları `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` Visual Studio başladığında yüklenir. Bu nedenle, yeni dosya test etmek için Visual Studio'yu yeniden başlatın.  
  
7.  İçinde **Çözüm Gezgini**, bir projeye sağ tıklayın ve ardından **özellikleri**. İçinde **özellik sayfaları** pencerede sol bölmede, kural adıyla yeni bir düğüm olduğunu doğrulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
