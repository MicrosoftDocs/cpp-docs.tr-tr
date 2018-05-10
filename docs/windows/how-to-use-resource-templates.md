---
title: 'Nasıl yapılır: kaynak şablonlarını kullanma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- language-specific template files
- resource templates
- resources [Visual Studio], creating
- rct files
- templates, resource templates
- resources [Visual Studio], templates
- .rct files
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 534a86d10a4bcbc34e6cef29fbb77d7caa2c64b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-use-resource-templates"></a>Nasıl Yapılır: Kaynak Şablonlarını Kullanma
Kaynak şablon bir .rct dosyası olarak kaydettiğiniz özelleştirilmiş bir kaynaktır. Bir kaynak şablonu diğer kaynakları oluşturmak için bir başlangıç noktası olarak hizmet verebilir. Kaynak şablonları, ek kaynaklar veya standart denetimler gibi özellikleri ve diğer yinelenen öğeleri paylaşan kaynak grupları geliştirmede zaman kazandırır. Örneğin, bir Yardım düğmesi ve bir şirket logosu, bir simge birkaç iletişim kutularında eklemek isteyebilirsiniz. Böylece hızlı bir şekilde yapmak için yeni bir iletişim kutusu şablonu oluşturun ve logo ve Yardım düğmesini özelleştirme.  
  
 Kaynak şablonu özelleştirdikten sonra şablonu klasöründe (veya INCLUDE yolunda belirtilen herhangi bir yere) yaptığınız değişiklikleri kaydetmeniz gerekir böylece yeni kaynak şablonu kendi kaynak türünün altında görünür [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md). Ardından yeni kaynak şablonu sıklıkta gerektiği gibi kullanabilirsiniz.  
  
> [!NOTE]
>  Dile özgü şablon dosyalarını ana şablon dizini dizinlerde yerleştirebilirsiniz. Örneğin, yalnızca İngilizce şablon dosyalarında yerleştirebilirsiniz \\< kaynak şablonu dizini\>\1033.  
  
### <a name="to-create-a-template-for-resources"></a>Kaynaklar için bir şablon oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, projenize sağ tıklayın.  
  
2.  Kısayol menüsünden **Ekle**, ardından **Yeni Öğe Ekle**.  
  
3.  İçinde **Yeni Öğe Ekle** iletişim kutusunda **şablonları:** bölmesinde seçin **kaynak şablon dosyası (.rct)**.  
  
4.  Bir ad ve konum yeni .rct dosyanız için sağlayın ve tıklatın **açık**.  
  
5.  Yeni .rct dosyayı projenize eklenir ve altında Çözüm Gezgini'nde görüntülenir **kaynakları** klasör.  
  
     Şimdi, bir belge penceresinde açmak için .rct dosyasını çift tıklatın ardından kaynakları ekleyin (belge penceresinde dosyasını sağ tıklatın ve seçin **kaynak ekleme** kısayol menüsünde). Sonra bu kaynakları özelleştirebilir ve .rct dosyasını kaydedin.  
  
    > [!NOTE]
    >  Yeni bir RCT dosyası oluşturduğunuzda, Visual Studio için \Program Visual Studio 9.0\VC\VCResourceTemplates içinde \Program Visual Studio 9.0\VC\VCResourceTemplates arar\\*LCID* () 1033 İngilizce için) gibi *veya* üzerinde herhangi bir yere [yolunu](../windows/how-to-specify-include-directories-for-resources.md). RCT dosyaları başka bir dosya klasöre depolamak tercih ederseniz, örneğin \My belgeleri, yalnızca bu klasör için Include yolu eklemeniz gerekir ve Visual Studio RCT dosyanızı bulabilirsiniz.  
  
### <a name="to-convert-an-existing-rc-file-to-an-rct-file"></a>Var olan bir .rc dosyasını bir .rct dosyasına dönüştürmek için  
  
1.  [Tek başına bir dosya olarak .rc dosyasını açın](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
2.  Üzerinde **dosya** menüsünde tıklatın **kaydetmek \< *, filename*> olarak**.  
  
3.  Bir konum belirtin ve tıklatın **Tamam**.  
  
### <a name="to-create-a-new-resource-from-a-template"></a>Bir şablondan yeni bir kaynak oluşturmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md) bölmesinde .rc dosyasını sağ tıklatın ve seçin **kaynak ekleme** kısayol menüsünden.  
  
2.  İçinde **kaynak ekleme** iletişim kutusunda, artı işaretini tıklatın (**+**) kaynak düğümünü genişletin ve bu kaynak için mevcut tüm şablonları görmek için bir kaynak yanındaki.  
  
3.  Kullanmak istediğiniz şablonu çift tıklatın.  
  
4.  Eklenen kaynak, kaynak düzenleyicisinde gerektiği gibi değiştirin.  
  
     Kaynak Düzenleyicisi'ni otomatik olarak bir benzersiz kaynak kimliği sağlar Gözden geçirebilirsiniz [kaynak özelliklerini](../windows/changing-the-properties-of-a-resource.md) gerektiğinde.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.*  
  
 Gereksinimler  
  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaynak dosyaları](../windows/resource-files-visual-studio.md)   
 [Kaynak Düzenleyicileri](../windows/resource-editors.md)