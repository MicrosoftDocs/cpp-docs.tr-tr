---
title: (Simgeler için görüntü Düzenleyicisi) görüntünün parçalarını düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b33a591a2f38062b5eaf81b0f56ab73a36f4c90c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>Görüntünün Parçalarını Düzenleme (Simgeler İçin Görüntü Düzenleyicisi)
Standart düzenleme işlemleri gerçekleştirebilir — kesme, kopyalama, silme ve taşıma — üzerinde bir [seçimi](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), görüntünün tamamını veya yalnızca bir kısmını seçim olup olmadığını. Görüntü Düzenleyicisi Windows panosuna kullandığı için görüntü Düzenleyicisi'ni ve Windows için diğer uygulamalar arasında görüntüleri aktarabilirsiniz.  
  
 Ayrıca, görüntünün tamamını veya yalnızca bir bölümü içerip seçimi yeniden boyutlandırabilirsiniz.  
  
### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>Geçerli seçimi Kes ve panoya taşımak için  
  
1.  Tıklatın **Kes** üzerinde **Düzenle** menüsü.  
  
### <a name="to-copy-the-selection"></a>Seçimi kopyalamak için  
  
1.  Seçim kenarlığının içinde veya herhangi bir işaretçi üzerinde boyutlandırma dışında getirin.  
  
2.  Basılı **CTRL** anahtar seçimi yeni bir konuma sürükleyin. Özgün seçim alanı değiştirilmez.  
  
3.  Geçerli konumuna görüntüsüne seçimi kopyalayın için seçim imleci dışında ek Yardım düğmesini tıklatın.  
  
### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Bir görüntüye Pano içeriği yapıştırmak için  
  
1.  Gelen **Düzenle** menüsünde seçin **Yapıştır**.  
  
     Seçimi, kenarlığı Pano içeriğini bölmenin sol üst köşesinde görüntülenir.  
  
2.  Seçimin kenarlık işaretçinin getirin ve görüntünün görüntü üzerinde istenen konuma sürükleyin.  
  
3.  Görüntünün yeni konumunda bağlantı için seçim kenarlığı dışında ek Yardım düğmesini tıklatın.  
  
### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Geçerli seçim panoya taşımadan silmek için  
  
1.  Gelen **Düzenle** menüsünde seçin **silmek**.  
  
     Seçimin özgün alan geçerli arka plan rengiyle doldurulur.  
  
    > [!NOTE]
    >  Erişim kesme, kopyalama, yapıştırma ve Kaynak Görünümü penceresi sağ tıklayarak komutları silin.  
  
### <a name="to-move-the-selection"></a>Seçimi taşımak için  
  
1.  Seçim kenarlığının içinde veya herhangi bir işaretçi üzerinde boyutlandırma dışında getirin.  
  
2.  Seçimi yeni konumuna sürükleyin.  
  
3.  Yeni konumunda görüntüdeki seçimi bağlamak için seçim kenarlığı dışında'ı tıklatın.  
  
 Bir seçim ile çizim hakkında daha fazla bilgi için bkz: [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
 Gereksinimler  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)   
 [Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)

