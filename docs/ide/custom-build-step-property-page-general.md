---
title: 'Özel derleme adımı özellik sayfası: Genel | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCCustomBuildStep.AdditionalInputs
- VC.Project.VCCustomBuildStep.CustomBuildAfterTargets
- VC.Project.VCCustomBuildStep.CustomBuildBeforeTargets
- VC.Project.VCCustomBuildStep.Outputs
- VC.Project.VCCustomBuildStep.Message
- VC.Project.VCCustomBuildStep.Command
dev_langs:
- C++
helpviewer_keywords:
- project properties, custom build step
- custom build step (general)
ms.assetid: bd319741-0491-46c4-a428-7c61b4b46a02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: df655f06d3b6d6b2b7b36f83f7c109adce758fef
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45722000"
---
# <a name="custom-build-step-property-page-general"></a>Özel Derleme Adımı Özellik Sayfası: Genel
Projenizdeki her bir proje yapılandırması ve hedef platform bileşimi için, proje oluşturulduğunda gerçekleştirilecek özel bir adım belirtebilirsiniz.  

Bu sayfa Linux sürümü için bkz: [özel derleme adımı özellikleri (Linux C++)](../linux/prop-pages/custom-build-step-linux.md).
  
## <a name="uielement-list"></a>UIElement Listesi  
- **Komut satırı**

   Özel derleme adımı tarafından yürütülecek komut.  
  
- **Açıklama**

   Özel derleme adımı çalıştırıldığında görüntülenen ileti.  
  
- **çıkışlar**

   Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir.  
  
- **Ek Bağımlılıklar**

   Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi.  
  
- **Sonra yürütme ve önce yürütme**

   Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir.  
  
- **Çıkışı içerik olarak değerlendir**

   Bu seçenek, yalnızca tüm içerik dosyalarını .appx paketine dahil, Evrensel Windows platformu veya Windows Phone uygulamaları için daha anlamlı olur.  
  
### <a name="to-specify-a-custom-build-step"></a>Özel derleme adımı belirtmek için  
  
1.  Menü çubuğunda, **proje**, **özellikleri**. Daha fazla bilgi için [Working with Project Properties](../ide/working-with-project-properties.md).  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda, gitmek **yapılandırma özellikleri**, **özel derleme adımı**, **genel** sayfası.  
  
3.  Ayarları değiştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik Sayfaları](../ide/property-pages-visual-cpp.md)