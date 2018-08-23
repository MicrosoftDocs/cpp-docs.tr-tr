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
ms.openlocfilehash: 0380fd6fc9b37c4d7458453398cfbd2ce6699234
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607839"
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>Görüntünün Parçalarını Düzenleme (Simgeler İçin Görüntü Düzenleyicisi)

Standart düzenleme işlemleri gerçekleştirebileceğiniz — kesme, kopyalama, silme ve taşıma — üzerinde bir [seçimi](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), görüntünün tamamını veya yalnızca bir kısmını seçim olup olmadığını. Çünkü **görüntü** Düzenleyicisi kullanan **Windows Pano**, görüntülerin arasında aktarabilirsiniz **görüntü** Düzenleyicisi ve diğer uygulamalar için Windows.

Ayrıca, görüntünün tamamını veya bir bölümünü içerip içermediğini seçimi yeniden boyutlandırabilirsiniz.

### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>Geçerli seçimi kesip panoya Taşı

1. Tıklayın **Kes** üzerinde **Düzenle** menüsü.

### <a name="to-copy-the-selection"></a>Seçimi kopyalamak için

1. Seçim kenarlığı içinde veya herhangi bir işaretçiyi üzerinde boyutlandırma dışında tutun.

2. Basılı **Ctrl** anahtar seçimi yeni bir konuma sürükleyin. Özgün seçim alanı değiştirilmez.

3. Kendi geçerli konumunda görüntüye Seçimi kopyalamak için seçimi imleci tıklayın.

### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Pano içeriğini bir görüntüye yapıştırmak için

1. Gelen **Düzenle** menüsünde seçin **Yapıştır**.

   Seçimi kenarlıkla Pano içeriğini bölmesinin sol üst köşesinde görünür.

2. Seçim kenarlığı içinde işaretçiyi ve görüntünün görüntü üzerinde istenen konuma sürükleyin.

3. Görüntünün yeni konumunda yer işareti için seçim kenarlığı dışında ek Yardım düğmesini tıklatın.

### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Geçerli seçimi panoya taşımadan silmek için

1. Gelen **Düzenle** menüsünde seçin **Sil**.

   Özgün alan seçimin geçerli arka plan rengi ile doldurulur.

   > [!NOTE]
   > Erişebildiğiniz **Kes**, **kopyalama**, **Yapıştır**, ve **Sil** sağ tıklayarak, komutları **KaynakGörünümü** penceresi.

### <a name="to-move-the-selection"></a>Seçimi taşımak için

1. Seçim kenarlığı içinde veya herhangi bir işaretçiyi üzerinde boyutlandırma dışında tutun.

2. Seçimi yeni konumuna sürükleyin.

3. Görüntüdeki yeni konumunda seçimi bağlantı eklemek için seçim kenarlığı tıklayın.

Çizim ile bir seçim hakkında daha fazla bilgi için bkz. [özel Fırça oluşturma](../windows/creating-a-custom-brush-image-editor-for-icons.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Yok.

## <a name="see-also"></a>Ayrıca Bkz.

[Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)  
[Grafik kaynakları düzenleme](../windows/editing-graphical-resources-image-editor-for-icons.md)  
[Simgeler için Görüntü Düzenleyicisi](../windows/image-editor-for-icons.md)