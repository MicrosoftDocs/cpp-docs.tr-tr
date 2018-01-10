---
title: "Bir kaynağı ikili düzenleme için açma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.binary
dev_langs: C++
helpviewer_keywords:
- binary data, editing
- resources [Visual Studio], opening for binary editing
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 92a0c0459626f139b7a8d7ae2313439c66d2a11c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="opening-a-resource-for-binary-editing"></a>Kaynağı İkili Düzenleme İçin Açma
### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>İkili düzenleme için bir Windows Masaüstü kaynak açmak için  
  
1.  İçinde [kaynak görünümü](../windows/resource-view-window.md), düzenlemek istediğiniz belirli bir kaynak dosyasını seçin.  
  
    > [!NOTE]
    >  Projenizi bir .rc dosyası yoksa, lütfen bkz [yeni bir kaynak betik dosyası oluşturma](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Kaynak sağ tıklatın ve **açık ikili veri** kısayol menüsünden.  
  
    > [!NOTE]
    >  Kullanırsanız [kaynak görünümü](../windows/resource-view-window.md) Visual Studio (RCDATA veya özel bir kaynak gibi), kaynak tanımadığı biçimiyle kaynak penceresini İkili Düzenleyicisi'nde otomatik olarak açılır.  
  
### <a name="to-open-a-managed-resource-for-binary-editing"></a>İkili düzenleme için yönetilen bir kaynağın açmak için  
  
1.  Çözüm Gezgini'nde, düzenlemek istediğiniz belirli bir kaynak dosyası seçin.  
  
2.  Kaynak sağ tıklatın ve seçin **birlikte Aç** kısayol menüsünden.  
  
3.  İçinde **birlikte Aç** iletişim kutusunda, seçin **İkili Düzenleyicisi**.  
  
    > [!NOTE]
    >  Kullanabileceğiniz [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md) ve [İkili Düzenleyicisi](binary-editor.md) yönetilen projelerde kaynak dosyalarıyla çalışmak için. Düzenlemek istediğiniz yönetilen kaynaklar, bağlı kaynaklar olmalıdır. Visual Studio kaynak düzenleyicileri eklenmiş kaynakları düzenlemeyi desteklemez.  
  
    > [!NOTE]
    >  Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).   
  
 ![İkili Düzenleyicisi](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")  
İkili Düzenleyicisi'nde görüntülenen bir iletişim kutusu için ikili veriler  
  
 Yalnızca belirli ASCII değerleri (0x20 0x7E aracılığıyla) İkili Düzenleyicisi'nde gösterilir. Genişletilmiş karakterler, nokta İkili Düzenleyicisi (sağ panelde) ASCII değeri bölümünde görüntülenir. "Yazdırılabilir" karakterleri ASCII 32 126 aracılığıyla değerlerdir.  
  
> [!NOTE]
>  Zaten başka bir Düzenleyicisi penceresinde düzenlenen bir kaynakta İkili Düzenleyicisi kullanmak istiyorsanız, önce diğer Düzenleyicisi penceresini kapatın.  
  
 **Gereksinimler**  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İkili Düzenleyicisi](binary-editor.md)

