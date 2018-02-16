---
title: "Özel derleme adımı özellik sayfası: Genel | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e57d6cf00843cd6604ef269235602ea1b5b5e9b
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="custom-build-step-property-page-general"></a>Özel Derleme Adımı Özellik Sayfası: Genel
Projenizdeki her bir proje yapılandırması ve hedef platform bileşimi için, proje oluşturulduğunda gerçekleştirilecek özel bir adım belirtebilirsiniz.  

Bu sayfayı Linux sürümü için bkz: [özel derleme adımı özellikleri (Linux C++)](../linux/prop-pages/custom-build-step-linux.md).
  
## <a name="uielement-list"></a>UIElement Listesi  
 Komut satırı  
 Özel derleme adımı tarafından yürütülecek komut.  
  
 **Açıklama**  
 Özel derleme adımı çalıştırıldığında görüntülenen ileti.  
  
 **Çıkışları**  
 Özel derleme adımının oluşturduğu çıkış dosyası. Artımlı derlemelerin doğru çalışması için bu ayar gereklidir.  
  
 Ek Bağımlılıklar  
 Özel derleme adımı için kullanılacak tüm ek girdi dosyalarının noktalı virgülle ayrılmış listesi.  
  
 Sonra yürütün ve önce yürütme  
 Bu seçenekler, listelenen hedeflere göreli olarak, özel derleme adımının yapı işleminde çalıştırılacağı zamanı tanımlar. Yapı işleminde en önemli adımları temsil etmeleri nedeniyle, en yaygın olarak listelenen hedefler BuildGenerateSources, BuildCompile ve BuildLink'tir. Sıklıkla listelenen diğer hedefler Midl, CLCompile ve Link'tir.  
  
 Çıkışı İçerik Olarak Değerlendir  
 Bu seçenek, yalnızca tüm içerik dosyalarının .appx paketinde pdb'lerini, Evrensel Windows platformu veya Windows Phone uygulamaları için anlamlıdır.  
  
### <a name="to-specify-a-custom-build-step"></a>Özel derleme adımı belirtmek için  
  
1.  Menü çubuğunda seçin **proje**, **özellikleri**. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
2.  İçinde **özellik sayfaları** iletişim kutusunda, gitmek **yapılandırma özellikleri**, **özel derleme adımı**, **genel** sayfası.  
  
3.  Ayarları değiştirin.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özellik Sayfaları](../ide/property-pages-visual-cpp.md)