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
ms.openlocfilehash: c90367a1db313de1935e119c2efb8e9713b3d282
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603609"
---
# <a name="selecting-an-area-of-an-image-image-editor-for-icons"></a>Görüntü Alanını Seçme (Simgeler İçin Görüntü Düzenleyicisi)

Seçim araçları, kesme, kopyalama, Temizle, yeniden boyutlandırma, Ters Çevir veya taşımak istediğiniz görüntüyü bir alanı tanımlamak için kullanabilirsiniz. İle **dikdörtgen seçim** aracı tanımlayabilir ve görüntünün dikdörtgen bir bölge seçin. İle **düzensiz seçim** aracı seçmek için kesme, kopyalama veya başka bir işlem için istediğiniz alanı serbest bir özetini çizebilir.

> [!NOTE]
> Bkz: **dikdörtgen seçim** ve **düzensiz seçim** araçları Resimli olarak [Resim Düzenleyicisi araç çubuğu](../windows/toolbar-image-editor-for-icons.md) veya herdüğmeileilişkiliaraçipuçlarınıgörüntüleyin**Resim Düzenleyicisi** araç çubuğu.

Özel fırça seçimden de oluşturabilirsiniz. Daha fazla bilgi için [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).

### <a name="to-select-an-area-of-an-image"></a>Görüntünün bir alan seçmek için

1. Üzerinde **Resim Düzenleyicisi** araç çubuğu (veya **görüntü** menüsünde **Araçları** komut), istediğiniz Seçim Aracı'nı tıklatın.

2. Ekleme noktasını seçmek istediğiniz görüntü alan bir köşesine taşıyın. Ekleme noktasını resminin üstündeyken işaretçileri görünür.

3. Ekleme noktasını seçmek istediğiniz alanın zıt köşe için sürükleyin. Hangi piksel seçili bir dikdörtgen gösterilir. Dikdörtgen altında dahil olmak üzere bu dikdörtgenin içindeki tüm piksel seçime dahil edilir.

4. Fare düğmesini bırakın. Seçili alanı seçim kenarlığı barındırır.

### <a name="to-select-an-entire-image"></a>Görüntünün tümünü seçmek için

1. Geçerli seçimi dışında görüntüye tıklayın. Seçim kenarlığı odak değiştikçe ve görüntünün tamamını yeniden kapsar.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)  
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)