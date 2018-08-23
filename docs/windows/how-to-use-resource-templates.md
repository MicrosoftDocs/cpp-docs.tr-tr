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
ms.openlocfilehash: 5bd85dd5c5b6468ca8246fdf11f4068eae928107
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602446"
---
# <a name="how-to-use-resource-templates"></a>Nasıl Yapılır: Kaynak Şablonlarını Kullanma

Kaynak şablon bir .rct dosyası olarak kaydettiğiniz bir özelleştirilmiş bir kaynaktır. Kaynak şablonu diğer kaynakları oluşturmak için bir başlangıç noktası olarak hizmet verebilir. Kaynak şablonları, ek kaynaklar ya da standart denetimler gibi özellikleri ve diğer yinelenen öğeleri paylaşan kaynakların grupları geliştirmede zamandan tasarruf edin. Örneğin, Yardım düğmesi ve bir şirket logosu simgesi birkaç iletişim kutularında eklemek isteyebilirsiniz. Kadar hızlı bir şekilde yapmak için yeni bir iletişim kutusu şablonu oluşturma ve Yardım düğmesini logosu ile özelleştirebilir.

Kaynak şablonu özelleştirdikten sonra şablonu klasörüne (veya INCLUDE yolu belirtilen herhangi bir konuma) yaptığınız değişiklikleri kaydetmeniz gerekir, böylece yeni kaynak şablonu kaynak türüne altında görünür [kaynak Ekle iletişim kutusu](../windows/add-resource-dialog-box.md). Ardından yeni kaynak şablonu sıklıkta gerektiği şekilde kullanabilirsiniz.

> [!NOTE]
> Dile özgü şablon dosyaları ana şablon dizininin alt dizinlerde yerleştirebilirsiniz. Örneğin, yalnızca İngilizce şablon dosyalarında yerleştirebilirsiniz \\< kaynak şablon dizini\>\1033.

### <a name="to-create-a-template-for-resources"></a>Kaynaklar için bir şablon oluşturmak için

1. İçinde **Çözüm Gezgini**, projenize sağ tıklayın.

2. Kısayol menüsünden **Ekle**, ardından **Yeni Öğe Ekle**.

3. İçinde **Yeni Öğe Ekle** iletişim kutusundaki **şablonları:** bölmesinde seçin **kaynak şablon dosyası (.rct)**.

4. Bir ad ve yeni .rct dosyanız için bir konum girin ve tıklatın **açık**.

5. Yeni .rct dosyası projenize eklenir ve görünür **Çözüm Gezgini** altında **kaynakları** klasör.

   Artık, bir belge penceresi açın .rct dosyasına çift tıklayarak sonra kaynakları ekleyin (belge penceresinde dosyasını sağ tıklatın ve seçin **kaynak Ekle** kısayol menüsünden). Ardından, bu kaynakları özelleştirebilir ve .rct dosyayı kaydedin.

   > [!NOTE]
   > Yeni bir RCT dosyası oluşturduğunuzda, Visual Studio için Visual Studio 9.0\VC\VCResourceTemplates \Program içinde \Program Visual Studio 9.0\VC\VCResourceTemplates arar\\*LCID* () 1033 İngilizce için) gibi *veya* yerinde [yolunu](../windows/how-to-specify-include-directories-for-resources.md). RCT dosyaları başka bir dosya klasöre depolamak isterseniz, örneğin \My belgeler, yalnızca bu klasör yoluna eklemeniz gerekir ve Visual Studio RCT dosyanızı bulabilirsiniz.

### <a name="to-convert-an-existing-rc-file-to-an-rct-file"></a>Var olan bir .rc dosyasını bir .rct dosyasına dönüştürmek için

1. [Tek başına bir dosya olarak .rc dosyasını açın](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

2. Üzerinde **dosya** menüsünde tıklatın **Kaydet \< *, filename*> olarak**.

3. Bir konum belirtin ve tıklayın **Tamam**.

### <a name="to-create-a-new-resource-from-a-template"></a>Bir şablondan yeni bir kaynak oluşturmak için

1. İçinde [kaynak görünümü](../windows/resource-view-window.md) bölmesinde .rc dosyasını sağ tıklatın ve seçin **kaynak Ekle** kısayol menüsünden.

2. İçinde **kaynak Ekle** iletişim kutusunda, artı işaretine tıklayın (**+**) kaynak düğümünü genişletin ve o kaynak için mevcut tüm şablonları görmek için bir kaynak yanında.

3. Kullanmak istediğiniz şablonu çift tıklatın.

4. Eklenen kaynak, kaynak düzenleyicisinde gerektiği gibi değiştirin.

   Kaynak Düzenleyicisi bir kaynağın benzersiz kimliği otomatik olarak sağlar. Düzeltebilir [kaynak özellikleri](../windows/changing-the-properties-of-a-resource.md) gerektiğinde.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak dosyaları](../windows/resource-files-visual-studio.md)  
[Kaynak Düzenleyicileri](../windows/resource-editors.md)