---
title: (Simgeler için görüntü Düzenleyicisi) görüntüyü yeniden boyutlandırma | Microsoft Docs
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
- Image editor [C++], resizing images
- graphics [C++], resizing
- images [C++], resizing
- resizing images
ms.assetid: d83a02c4-4dfe-4586-a0df-51a50c2ba71d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9c972f4038da4b4ed1d52fee0b8029b6f48ff3bb
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40013879"
---
# <a name="resizing-an-image-image-editor-for-icons"></a>Görüntüyü Yeniden Boyutlandırma (Simgeler İçin Görüntü Düzenleyicisi)
Davranışını **görüntü** görüntüyü yeniden boyutlandırma sırasında Düzenleyicisi bağlı olup seçtiğiniz [seçili](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) görüntünün tamamını veya yalnızca bir bölümü.  
  
 Seçimi görüntüsü yalnızca bir bölümünü içerdiğinde **görüntü** Düzenleyicisi satırları veya sütunları piksel silme ve arka plan rengiyle boşaltılmış bölgeleri girerek seçim daraltır ya da seçimi uzatır Satırlar veya sütunlar piksel çoğaltma.  
  
 Seçimi görüntünün tamamını içerdiği durumlarda **görüntü** Düzenleyici ya da daraltır ve resmi uzatır veya kırpar ve genişletir.  
  
 Görüntüyü yeniden boyutlandırma için iki mekanizma vardır: boyutlandırma ve [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Görüntünün bir parçasını ve tüm boyutunu değiştirmek için boyutlandırma tutamaçlarını sürükleyebilirsiniz. Sürükleyebilirsiniz boyutlandırma tutamaçlarını dolu. Boş tanıtıcıları sürükleyemezsiniz. Kullanabileceğiniz **özellikleri** tamamını yeniden boyutlandırmak için pencere görüntü yalnızca seçili bir parçası değil.  
  
 ![Boyutlandırma tutamaçları üzerinde bir bit eşlem](../mfc/media/vcimageeditorsizinghandles.gif "vcImageEditorSizingHandles")  
Boyutlandırma  
  
> [!NOTE]
>  Varsa **döşeme Kılavuzu** seçeneğe [kılavuz Ayarları iletişim kutusu](../windows/grid-settings-dialog-box-image-editor-for-icons.md), ardından sonraki kutucuğu kılavuz çizgisi yapışır yeniden boyutlandırma. Yalnızca **piksel kılavuzunu** seçeneği (varsayılan ayar) seçili, sonraki kullanılabilir piksel yapışır yeniden boyutlandırma.  
  
-   [Görüntünün tümünü yeniden boyutlandırma](../windows/resizing-an-entire-image-image-editor-for-icons.md)  
  
-   [Kırpma veya genişletme görüntünün](cropping-or-extending-an-entire-image-image-editor-for-icons.md)  
  
-   [Tümünü küçültme veya uzatma görüntünün](../windows/shrinking-or-stretching-an-entire-image-image-editor-for-icons.md)  
  
-   [Tümünü küçültme veya uzatma bir görüntünün parçası](../windows/shrinking-or-stretching-part-of-an-image-image-editor-for-icons.md)  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)