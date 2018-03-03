---
title: "Görüntünün (simgeler için görüntü Düzenleyicisi) yeniden boyutlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8f856c5cf825fd9032ce64afbd09d3bed83ea40f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Görüntüyü Yeniden Boyutlandırma (Simgeler İçin Görüntü Düzenleyicisi)
Görüntüyü yeniden boyutlandırma sırasında görüntü Düzenleyicisi davranışı olduğunuz olup bağlıdır [seçili](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) görüntünün tamamını veya yalnızca parçası.  
  
 Seçimi görüntünün yalnızca bir parçasının içerdiğinde, satırları silme Seçimi görüntü Düzenleyicisi küçültür veya piksel ve geçerli arka plan rengini veya, ile vacated bölgeler doldurma sütunlarının satır veya sütun piksel çoğaltarak seçimi genişletir.  
  
 Seçimi görüntünün tamamını içerdiğinde, görüntü Düzenleyicisi ya da küçültür resmi uzatır veya kırpar ve onu genişletir.  
  
 Görüntüyü yeniden boyutlandırma için iki mekanizma vardır: boyutlandırma ve [Özellikler penceresini](/visualstudio/ide/reference/properties-window). Görüntünün bir parçasını ve tüm boyutunu değiştirmek için boyutlandırma sürükleyebilirsiniz. Sürükleyebilirsiniz boyutlandırma dolu. Boş tanıtıcıları sürükleyin olamaz. Görüntünün tümünü yalnızca, yeniden boyutlandırmak için Özellikler penceresini seçilen bir bölümünü kullanabilirsiniz.  
  
 ![Bir bit eşlem üzerinde boyutlandırma](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
Boyutlandırma  
  
> [!NOTE]
>  Belirtilen döşeme kılavuz seçeneğe varsa [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md), sonraki döşeme kılavuz çizgisi yapışır yeniden boyutlandırma. Yalnızca seçenek piksel kılavuzunu (varsayılan ayar), seçili sonraki kullanılabilir piksel yapışır yeniden boyutlandırma.  
  
-   [Görüntünün tümünü yeniden boyutlandırma](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Kırpma veya görüntünün tümünü genişletme](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Tüm görüntünün küçültme veya uzatma](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Küçültme veya görüntünün bir parçasını uzatma](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

