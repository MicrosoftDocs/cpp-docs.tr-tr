---
title: "Nasıl yapılır: özel araçlarla proje özelliklerini tümleştirme | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: msbuild.cpp.howto.integratecustomtools
dev_langs: C++
helpviewer_keywords: 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 128b19c1175fb5f39599a9ccaeae66d1fc53fdab
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Nasıl Yapılır: Özel Araçlarla Proje Özelliklerini Tümleştirme
Visual Studio özel araç seçenekleri ekleyebilirsiniz **özellik sayfaları** bir temel alınan XML şema dosyası oluşturarak penceresi.  
  
 **Yapılandırma özellikleri** bölümünü **özellik sayfaları** pencere görüntüler olarak bilinen ayar grupları *kuralları*. Her kural bir araç veya bir Grup ayarlarını içerir. Örneğin, **bağlayıcı** kural bağlayıcı aracı ayarlarını içerir. Bir kural ayarlarında içine bölünmüştür *kategorileri*.  
  
 Bu belgede özel aracınız özellikleri içerir ve böylece Visual Studio başladığında özellikleri yüklenen bir kümesi dizindeki bir dosya oluşturma açıklanmaktadır. Dosyayı değiştirme hakkında daha fazla bilgi için bkz: [Platform Extensibilty Kısım 2](http://go.microsoft.com/fwlink/?LinkID=191489) Visual Studio Proje Ekibi blogunda.  
  
### <a name="to-add-or-change-project-properties"></a>Proje özellik eklemek veya değiştirmek için  
  
1.  XML Düzenleyicisi'nde, bir XML dosyası oluşturun.  
  
2.  Visual Studio 2017 dosyayı kaydetmek `VCTargets\1033` klasör. Yüklü Visual Studio 2017 her sürümü ve her dil için farklı bir yol gerekir. Örneğin, İngilizce Visual Studio Enterprise edition için klasör yolu `%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\VC\VCTargets\1033`. Visual Studio sürümü ve dili yolunu ayarlayın. Her kural **özellik sayfaları** penceresi bu klasörde bir XML dosyası ile temsil edilir. Dosyayı klasörde benzersiz olarak adlandırılır emin olun.  
  
3.  İçeriği Kopyala `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml`değişiklikleri kaydetmeden kapatın ve içeriği yeni XML dosyasında yapıştırın. Tüm XML şema dosyası kullanabilirsiniz - Bu tek bir şablonu ile başlayın, böylece kullanılabilir.  
  
4.  Yeni XML dosyasında içeriği, gereksinimlerinize göre değiştirin. Değiştirdiğinizden emin olun **kural adı** ve **Rule.DisplayName** dosyasının üstünde.  
  
5.  Değişiklikleri kaydetmek ve dosyayı kapatın.  
  
6.  XML dosyaları `%ProgramFiles%\Microsoft Visual Studio\2017\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` Visual Studio başladığında yüklenir. Bu nedenle, yeni dosyasını sınamak için Visual Studio'yu yeniden başlatın.  
  
7.  İçinde **Çözüm Gezgini**, bir projeye sağ tıklayın ve ardından **özellikleri**. İçinde **özellik sayfaları** pencerede, sol bölmede, kuralınızın adını sahip yeni bir düğüm olduğunu doğrulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MSBuild (Visual C++)](../build/msbuild-visual-cpp.md)
