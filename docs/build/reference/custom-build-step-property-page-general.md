---
title: 'Özel Derleme Adımı Özellik Sayfası: Genel'
description: Bu makalede, özellik sayfaları iletişim kutusunda özel derleme adımı sayfasında bulunan özellikler açıklanmaktadır.
ms.date: 10/27/2020
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
ms.openlocfilehash: 53f2deef931821981b3301f44ba37660975fb811
ms.sourcegitcommit: 9c801a43ee0d4d84956b03fd387716c818705e0d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/28/2020
ms.locfileid: "92907590"
---
# <a name="custom-build-step-property-page-general"></a>Özel Derleme Adımı Özellik Sayfası: Genel

Projenizdeki her proje yapılandırması ve hedef platform birleşimi için, proje oluşturulduğunda yürütülecek özel bir adım belirtebilirsiniz.

Bu sayfanın Linux sürümü için bkz. [özel derleme adımı özellikleri (Linux C++)](../../linux/prop-pages/custom-build-step-linux.md).

## <a name="general-page"></a>Genel sayfa

- **Komut satırı**

   Özel derleme adımı tarafından yürütülecek komut.

- **Açıklama**

   Özel derleme adımı çalıştırıldığında görüntülenen ileti.

- **Çıkışlar**

   Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir.

- **Ek bağımlılıklar**

   Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi.

- **Önce yürütün ve yürütmeden önce yürütün**

   Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. En yaygın olarak listelenen hedefler, `BuildGenerateSources` , `BuildCompile` ve, `BuildLink` Yapı işlemindeki önemli adımları temsil ettiğinden, ve ' dir. Genellikle listelenen diğer hedefler `Midl` , ve ' dir `CLCompile` `Link` .

- **Çıkışı İçerik Olarak Değerlendir**

   Bu seçenek yalnızca, paketteki tüm içerik dosyalarını içeren Evrensel Windows Platformu veya Windows Phone uygulamalar için anlamlıdır *`.appx`* .

### <a name="to-specify-a-custom-build-step"></a>Özel derleme adımı belirtmek için

1. Menü çubuğunda, **Proje**  >  **özellikleri** ' ni seçin. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**  >  **özel derleme adımı**  >  **genel** sayfasına gidin.

1. Ayarları değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[C++ proje özellik sayfası başvurusu](property-pages-visual-cpp.md)
