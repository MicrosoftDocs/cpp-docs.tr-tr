---
title: "Nasıl yapılır: hızlı erişim araç çubuğunu özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- quick access toolbar [MFC], customization
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f67d46640a1a4fadc6750ca34b05910902679440
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-customize-the-quick-access-toolbar"></a>Nasıl yapılır: Hızlı Erişim Araç Çubuğunu Özelleştirme
Hızlı Erişim Araç çubuğu (QAT) ya da uygulama düğmesinin yanındaki veya kategori sekmeleri altında görüntülendiğinde komut kümesini içeren özelleştirilebilir bir araç çubuğu bulunur. Aşağıdaki çizimde tipik hızlı erişim araç çubuğu gösterir.  
  
 ![MFC Şerit hızlı erişim araç çubuğu](../mfc/media/quick_access_toolbar.png "quick_access_toolbar")  
  
 Hızlı Erişim Araç özelleştirmek için içinde açın **özellikleri** penceresinde, kendi komutları değiştirebilir ve Şerit denetimi Önizleme.  
  
### <a name="to-open-the-quick-access-toolbar-in-the-properties-window"></a>Hızlı Erişim Araç Özellikler penceresinde açmak için  
  
1.  Visual Studio'da üzerinde **Görünüm** menüsünde tıklatın **kaynak görünümü**.  
  
2.  İçinde **kaynak görünümü**, tasarım yüzeyine görüntülemek için Şerit kaynağı çift tıklatın.  
  
3.  Tasarım yüzeyinde hızlı erişim araç çubuğu menüyü sağ tıklatın ve ardından **özellikleri**.  
  
## <a name="quick-access-toolbar-properties"></a>Hızlı Erişim Araç çubuğu özellikleri  
 Aşağıdaki tabloda hızlı erişim araç özelliklerini tanımlar.  
  
|Özellik|Tanım|  
|--------------|----------------|  
|QAT konumu|Uygulama başladığında hızlı erişim araç konumunu belirtir. Konumu ya da olabilir **yukarıda** veya **aşağıda** Şerit denetimi.|  
|QAT öğeleri|Hızlı Erişim Araç çubuğu için kullanılabilir olan komutlar belirtir.|  
  
#### <a name="to-add-or-remove-commands-on-the-quick-access-toolbar"></a>Eklemek veya hızlı erişim araç çubuğu komutlarını kaldırmak için  
  
1.  İçinde **özellikleri** penceresinde tıklatın **QAT öğeleri**ve üç nokta düğmesini tıklatıp **(...)** .  
  
2.  İçinde **QAT öğeleri Düzenleyicisi** iletişim kutusu, kullanım **Ekle** ve **kaldırmak** hızlı erişim araç çubuğundaki komutları listesini değiştirmek için düğmeler.  
  
3.  Bir komutun hem hızlı erişim araç çubuğu ve hızlı erişim araç çubuğu menüsünde görünmesini istiyorsanız, komut yanındaki kutuyu seçin. Komutun yalnızca menüsünde görünmesini istiyorsanız, kutunun işaretini kaldırın.  
  
## <a name="previewing-the-ribbon"></a>Şerit Önizleme  
 Hızlı Erişim Araç çubuğu komutlarını tasarım yüzeyine görünmez. Bunları görüntülemek için Şerit önizlemek veya uygulamayı çalıştırın.  
  
#### <a name="to-preview-the-ribbon-control"></a>Şerit denetimi önizlemek için  
  
-   Üzerinde **Şerit Düzenleyicisi araç**, tıklatın **Test Şerit**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Şerit Tasarımcısı (MFC)](../mfc/ribbon-designer-mfc.md)

