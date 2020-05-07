---
title: 'Nasıl Yapılır: Özel Araçlarla Proje Özelliklerini Tümleştirme'
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
# <a name="how-to-integrate-custom-tools-into-the-project-properties"></a>Nasıl Yapılır: Özel Araçlarla Proje Özelliklerini Tümleştirme

Temel alınan bir XML şema dosyası oluşturarak Visual Studio **Özellik sayfaları** penceresine özel araç seçenekleri ekleyebilirsiniz.

**Özellik sayfaları** penceresinin **yapılandırma özellikleri** bölümü, *kural*olarak bilinen ayar gruplarını görüntüler. Her kural bir araç veya bir özellik grubu için ayarları içerir. Örneğin, **bağlayıcı** kuralı bağlayıcı aracının ayarlarını içerir. Kuraldaki ayarlar alt *kategorilere*ayrılabilir.

Bu belgede, Visual Studio başlatıldığında özelliklerin yüklenebilmesi için özel araclarınızın özelliklerini içeren bir küme dizininde bir dosyanın nasıl oluşturulacağı açıklanmaktadır. Dosyanın nasıl değiştirileceği hakkında bilgi için bkz. Visual Studio proje ekibi blogu üzerinde [Platform Extensibilty Part 2](https://blogs.msdn.microsoft.com/vsproject/2009/06/18/platform-extensibility-part-2/) .

### <a name="to-add-or-change-project-properties"></a>Proje özellikleri eklemek veya değiştirmek için

1. XML düzenleyicisinde bir XML dosyası oluşturun.

1. Dosyayı Visual Studio `VCTargets\1033` klasörüne kaydedin. Visual Studio 'nun yüklü her sürümü ve her dil için farklı bir yolunuz olacak. Örneğin, Ingilizce 'deki Visual Studio 2019 Community Edition için varsayılan klasör yolu `C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\Common7\IDE\VC\VCTargets`. Diliniz ve Visual Studio sürümünüz için yolu ayarlayın. **Özellik sayfaları** penceresindeki her kural, bu KLASÖRDEKI bir XML dosyası tarafından temsil edilir. Dosyanın klasörde benzersiz olarak adlandırıldığından emin olun.

1. İçeriğini `%ProgramFiles%\Microsoft Visual Studio\2019\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>\cl.xml` (veya yolunuz ne olursa olsun) kopyalayın, değişiklikleri kaydetmeden kapatın ve sonra IÇERIĞI yeni XML dosyanıza yapıştırın. Herhangi bir XML şema dosyası kullanabilirsiniz; Bu yalnızca bir şablonla başlamanız için kullanılabilir.

1. Yeni XML dosyasında, içeriği gereksinimlerinize göre değiştirin. Dosyanın en üstündeki **kural adı** ve **kural. DisplayName** ' i değiştirdiğinizden emin olun.

1. Değişiklikleri kaydedin ve dosyayı kapatın.

1. Visual Studio başlatıldığında `%ProgramFiles%\Microsoft Visual Studio\2019\<VS Edition>\Common7\IDE\VC\VCTargets\<LCID>` (veya kaydettiğiniz her yerde) XML dosyaları yüklenir. Bu nedenle, yeni dosyayı test etmek için Visual Studio 'Yu yeniden başlatın.

1. **Çözüm Gezgini**, bir projeye sağ tıklayın ve ardından **Özellikler**' e tıklayın. **Özellik sayfaları** penceresindeki sol bölmede kuralınız adına sahip yeni bir düğüm olduğunu doğrulayın.

## <a name="see-also"></a>Ayrıca bkz.

[Komut satırında MSBuild-C++](msbuild-visual-cpp.md)
