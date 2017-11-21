---
title: "(Simgeler için görüntü Düzenleyicisi) cihaz görüntülerinde saydam veya ters bölgeler oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cursors [C++], screen regions
- inverse colors, device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices, transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects, transparent images
- icons [C++], screen regions
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a1e59f05c011f1a65937c63f43bd8dfd6f506fe9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="creating-transparent-or-inverse-regions-in-device-images-image-editor-for-icons"></a>Cihaz Görüntülerinde Saydam veya Ters Bölgeler Oluşturma (Simgeler İçin Görüntü Düzenleyicisi)
İçinde [görüntü Düzenleyicisi](../windows/image-editor-for-icons.md), ilk simgesi veya imleci resmin saydam bir özniteliğine sahip. Simge ve imleci görüntüleri dikdörtgen olsa da, görüntünün parçalarını saydam olduğundan çoğu bunu görünmez; temel alınan görüntünün ekranında simgesi veya imleci gösterir. Simge sürüklediğinizde görüntünün parçalarını ters renkte görünebilir. Ekran renkleri ters renkte ayarlayarak bu efekti oluşturmak [renkler penceresi](../windows/colors-window-image-editor-for-icons.md).  
  
 Ekran ve tersi renkleri simgeleri uygulanır ve İmleçler şekil ve türetilmiş görüntü renk veya ters bölgeler atayın. Renkleri özniteliklerle sahip olmak görüntünün parçalarını gösterir. Düzenleme ekran rengi ve renk ters özniteliklerini temsil eden renkleri değiştirebilirsiniz. Bu değişiklikler simgesi veya imleci uygulamanızda görünümünü etkilemez.  
  
> [!NOTE]
>  Gördüğünüz iletişim kutuları ve menü komutları, etkin ayarlarınıza ve ürün sürümüne bağlı olarak Yardım menüsünde açıklanana göre farklılık gösterebilir. Ayarlarınızı değiştirmek için tercih **içeri ve dışarı aktarma ayarları** üzerinde **Araçları** menüsü. Daha fazla bilgi için bkz: [Visual Studio'da geliştirme ayarlarını özelleştirme](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-transparent-or-inverse-regions"></a>Saydam veya ters bölgeler oluşturmak için  
  
1.  İçinde **renkleri** penceresinde tıklatın **ekran rengi** Seçici veya **ters renk** Seçici.  
  
2.  Ekran veya bir çizim aracı kullanarak görüntünüzü üzerine ters renk uygulayın. Çizim Araçları ile ilgili daha fazla bilgi için bkz: [bir çizim aracı kullanma](using-a-drawing-tool-image-editor-for-icons.md).  
  
### <a name="to-change-the-screen-or-inverse-color"></a>Ekran veya ters rengini değiştirmek için  
  
1.  Şunlardan birini seçin **ekran rengi** Seçici veya **ters renk** Seçici.  
  
2.  Bir renk seçin **renkleri** palette **renkleri** penceresi.  
  
     Tamamlayıcı renk diğer seçicisini otomatik olarak atanır.  
  
    > [!TIP]
    >  Ekran rengi veya ters Renk Seçici çift tıklarsanız [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) görüntülenir.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
 Gereksinimler  
  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Simgeler ve İmleçler: görüntüleme cihazları için görüntü kaynakları](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

