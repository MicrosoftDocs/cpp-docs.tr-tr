---
title: "Görüntünün (simgeler için görüntü Düzenleyicisi) yeniden boyutlandırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.image.editing
dev_langs: C++
helpviewer_keywords:
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6c6e8d5e4704f9dda9399d67de5b3d0f93d283a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

