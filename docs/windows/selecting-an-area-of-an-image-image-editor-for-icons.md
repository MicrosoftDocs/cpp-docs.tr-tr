---
title: (Simgeler için görüntü Düzenleyicisi) görüntü alanını seçme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], image selection
- Image editor [C++], selecting images
- images [C++], selecting
- cursors [C++], selecting areas of
ms.assetid: 8b6ce4ad-eba1-4ece-86ba-cea92c3edff2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 07cb7528e25604e873f6da92193a97cf79700799
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890126"
---
# <a name="selecting-an-area-of-an-image-image-editor-for-icons"></a>Görüntü Alanını Seçme (Simgeler İçin Görüntü Düzenleyicisi)
Seçim araçları, kesme, kopyalama, temizleyin, yeniden boyutlandırma, ters çevirme veya taşımak istediğiniz görüntünün bir alanını tanımlamak için kullanabilirsiniz. İle **dikdörtgen seçim** aracı tanımlayabilir ve görüntünün dikdörtgen bir bölge seçin. İle **düzensiz seçimi** aracı, seçmek istediğiniz kesme, kopyalama veya başka bir işlem için alanın serbest anahat çizin.  
  
> [!NOTE]
>  Bkz: **dikdörtgen seçim** ve **düzensiz seçimi** araçları gösterilen [görüntü Düzenleyicisi araç](../windows/toolbar-image-editor-for-icons.md) veya herdüğmeilişkiliaraçipuçlarınıgörüntülemek**Görüntü Düzenleyicisi** araç.  
  
 Özel fırça seçimden de oluşturabilirsiniz. Daha fazla bilgi için bkz: [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
### <a name="to-select-an-area-of-an-image"></a>Görüntünün bir alanını seçmek için  
  
1.  Üzerinde **görüntü Düzenleyicisi** araç çubuğu (veya **görüntü** menüsünde **Araçları** komutu), istediğiniz Seçim Aracı'nı tıklatın.  
  
2.  Ekleme noktasını seçmek istediğiniz görüntü alanını bir köşesine taşıyın. Ekleme noktasını görüntünün üzerine olduğunda işaretçileri görünür.  
  
3.  Ekleme noktasını seçmek istediğiniz alanın karşı köşeye sürükleyin. Dikdörtgene hangi piksel seçili gösterir. Dikdörtgen altında dahil olmak üzere bu dikdörtgenin içindeki tüm pikselleri seçim dahil edilir.  
  
4.  Fare düğmesini bırakın. Seçimin kenarlık seçilen alan barındırır.  
  
### <a name="to-select-an-entire-image"></a>Görüntünün tümünü seçmek için  
  
1.  Geçerli seçim dışındaki görüntüyü'ı tıklatın. Seçimin kenarlık odak değiştirir ve görüntünün tamamını yine kapsar.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

