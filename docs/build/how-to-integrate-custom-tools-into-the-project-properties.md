---
title: 'Nasıl yapılır: Özel araçlarla proje özelliklerini tümleştirme'
ms.date: 05/16/2019
helpviewer_keywords:
- 'msbuild (c++), howto: integrate custom tools'
ms.assetid: f32d91a4-44e9-4de3-aa9a-1c7f709ad2ee
ms.openlocfilehash: 0c0233ad6715a3adb7d47f021a87207f288d5139
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837026"
---
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Nasıl yapılır: Özel araçlarla proje özelliklerini tümleştirme

Visual Studio için özel araç seçenekleri ekleyebilirsiniz **özellik sayfaları** arka plandaki XML şema dosyası oluşturarak penceresi.

**Yapılandırma özellikleri** bölümünü **özellik sayfaları** pencere görüntüler olarak bilinen bir ayar grupları *kuralları*. Her kural için bir aracı veya bir Grup ayarlarını içerir. Örneğin, **bağlayıcı** kural bağlayıcı aracı ayarlarını içerir. Bir kural ayarlarında içine alt *kategorileri*.

Bu belgede, özel aracınızı özellikleri içerir ve böylece Visual Studio başladığında özellikleri yüklü bir kümesi dizindeki bir dosya oluşturmak açıklanmaktadır. Dosya değiştirme hakkında daha fazla bilgi için bkz: [Platform Extensibilty Kısım 2](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/) Visual Studio Proje Ekibi blogunda.

### <a name="to-add-or-change-project-properties"></a>Proje özellik eklemek veya değiştirmek için

1. XML Düzenleyicisi'nde bir XML dosyası oluşturun.

1. Visual Studio'da dosyayı kaydedin `VCTargets\1033` klasör. Yüklü Visual Studio'nun her sürümü ve her dil için farklı bir yol gerekir. Örneğin, Visual Studio 2019 Community sürümü İngilizce için varsayılan klasör yolu olan `C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\VC\VCTargets`. Dil ve Visual Studio sürüm yolunu ayarlayın. Her kuralda **özellik sayfaları** penceresi bu klasördeki bir XML dosyası ile temsil edilir. Dosyayı klasörde benzersiz şekilde adlandırılmıştır emin olun.

1. İçeriğini kopyalayın `%ProgramFiles%\Microsoft Visual Studio\2019\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml` (veya yolunuzu ne olursa olsun), değişiklikleri kaydetmeden kapatın ve ardından içeriği yeni XML dosyanıza yapıştırın. Herhangi bir XML şema dosyası kullanabilirsiniz - tek bir şablonla başlamak için kullanılabilecek budur.

1. Yeni XML dosyasında içerik gereksinimlerinize göre değiştirin. Değiştirdiğinizden emin olun **kural adı** ve **Rule.DisplayName** dosyanın üst.

1. Değişiklikleri kaydedin ve dosyayı kapatın.

1. XML dosyaları `%ProgramFiles%\Microsoft Visual Studio\2019\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` (veya kaydettiğiniz her yerde) Visual Studio başladığında yüklenir. Bu nedenle, yeni dosya test etmek için Visual Studio'yu yeniden başlatın.

1. İçinde **Çözüm Gezgini**, bir projeye sağ tıklayın ve ardından **özellikleri**. İçinde **özellik sayfaları** pencerede sol bölmede, kural adıyla yeni bir düğüm olduğunu doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

[MSBuild komut satırında - C++](msbuild-visual-cpp.md)
