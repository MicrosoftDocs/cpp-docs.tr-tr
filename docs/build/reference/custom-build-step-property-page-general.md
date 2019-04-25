---
title: 'Özel derleme adımı özellik sayfası: Genel'
ms.date: 11/04/2016
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
ms.openlocfilehash: 329923140cf5a8f05e5c032ddb9e25c0ea45ec2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62273085"
---
# <a name="custom-build-step-property-page-general"></a>Özel derleme adımı özellik sayfası: Genel

Projenizdeki her bir proje yapılandırması ve hedef platform bileşimi için, proje oluşturulduğunda gerçekleştirilecek özel bir adım belirtebilirsiniz.

Bu sayfa Linux sürümü için bkz: [özel derleme adımı özellikleri (Linux C++)](../../linux/prop-pages/custom-build-step-linux.md).

## <a name="uielement-list"></a>UIElement Listesi

- **Komut satırı**

   Özel derleme adımı tarafından yürütülecek komut.

- **Açıklama**

   Özel derleme adımı çalıştırıldığında görüntülenen ileti.

- **Çıkışlar**

   Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir.

- **Ek Bağımlılıklar**

   Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi.

- **Sonra yürütme ve önce yürütme**

   Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir.

- **Çıkışı içerik olarak değerlendir**

   Bu seçenek, yalnızca tüm içerik dosyalarını .appx paketine dahil, Evrensel Windows platformu veya Windows Phone uygulamaları için daha anlamlı olur.

### <a name="to-specify-a-custom-build-step"></a>Özel derleme adımı belirtmek için

1. Menü çubuğunda, **proje**, **özellikleri**. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. İçinde **özellik sayfaları** iletişim kutusunda, gitmek **yapılandırma özellikleri**, **özel derleme adımı**, **genel** sayfası.

1. Ayarları değiştirin.

## <a name="see-also"></a>Ayrıca bkz.

[C++ projesi özellik Sayfa başvurusu](property-pages-visual-cpp.md)
