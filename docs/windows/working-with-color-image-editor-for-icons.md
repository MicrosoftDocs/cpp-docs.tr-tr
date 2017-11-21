---
title: "Renk (simgeler için görüntü Düzenleyicisi) ile çalışma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.image.color
dev_langs: C++
helpviewer_keywords:
- images [C++], background colors
- Image editor [C++], Colors Palette
- colors [C++], image
- Colors Palette, Image editor
- palettes, Image editor colors
- foreground colors, Image editor
- colors [C++]
ms.assetid: d34ff96f-241d-494f-abdd-13811ada8cd3
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6afda534f55d3247f2df11c1a48d0157af245cf2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="working-with-color-image-editor-for-icons"></a>Renklerle Çalışma (Simgeler İçin Görüntü Düzenleyicisi)
Görüntü Düzenleyicisi özellikle işleyen ve renkleri özelleştirmek birçok özellik içerir. Ön plan veya arka plan rengini ayarlamak, sınırlanmış alanları renkle doldurma veya geçerli ön plan veya arka plan rengi olarak kullanılacak bir görüntü üzerinde bir renk seçin. Araçlarını kullanabileceğiniz [görüntü Düzenleyicisi araç](../windows/toolbar-image-editor-for-icons.md) renk paleti birlikte [renkler penceresi](../windows/colors-window-image-editor-for-icons.md) görüntüleri oluşturmak için.  
  
 Tüm renkleri tek renkli ve 16 renkli görüntüleri için renk paleti renkleri penceresinde gösterilir. Ek olarak 16 standart renkler, kendi özel renkler oluşturabilirsiniz. Palet renkleri hiçbirini değiştirilmesi görüntüdeki karşılık gelen renk hemen değiştirir.  
  
 Ne zaman 256-renk simgesi ve imleci ile çalışma görüntüleri, renkler özelliğinde [Özellikler penceresini](/visualstudio/ide/reference/properties-window) kullanılır. Daha fazla bilgi için bkz: [256-renk simgesi veya imleci oluşturma](creating-a-256-color-icon-or-cursor-image-editor-for-icons.md).  
  
> [!NOTE]
>  Resim Düzenleyicisi'ni kullanarak 32 bitlik resimleri görüntüleyebilirsiniz, ancak onları düzenleyemezsiniz.  
  
 TRUE renk görüntüleri de oluşturulabilir. Ancak, gerçek renk örnekleri tam palet renkleri penceresinde görüntülenmez; Bunlar yalnızca ön plan veya arka plan rengi göstergesi alanında görüntülenir. Doğru renkleri kullanarak oluşturulur [Özel Renk Seçici iletişim kutusu](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md). Daha fazla bilgi için bkz: [özelleştirme veya renklerini değiştirme](../windows/customizing-or-changing-colors-image-editor-for-icons.md).  
  
 Disk üzerinde özelleştirilmiş renk paletlerini kaydetme ve bunları gerektiği gibi yeniden yükleyin. En son kullanılan renk paletini kayıt defterinde kaydedilir ve Visual Studio'nun bir sonraki başlatışınızda otomatik olarak yüklenir.  
  
-   [Ön plan veya arka plan renklerini seçme](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md)  
  
-   [Sınırlı bir alanını renkle görüntünün doldurma](../windows/filling-a-bounded-area-of-an-image-with-a-color-image-editor-for-icons.md)  
  
-   [Başka yerde kullanmak üzere görüntüden renk alma](../windows/picking-up-a-color-from-an-image-to-use-elsewhere-image-editor-for-icons.md)  
  
-   [Saydam veya donuk arka plan seçme](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md)  
  
-   [Seçimdeki renkleri ters çevirme](../windows/inverting-the-colors-in-a-selection-image-editor-for-icons.md)  
  
-   [Renkleri özelleştirme veya değiştirme](../windows/customizing-or-changing-colors-image-editor-for-icons.md)  
  
-   [Renk paletlerini kaydetme ve farklı yükleme](../windows/saving-and-loading-different-color-palettes-image-editor-for-icons.md)  
  
-   [Renkler penceresi](../windows/colors-window-image-editor-for-icons.md)  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 Yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hızlandırıcı tuşları](../windows/accelerator-keys-image-editor-for-icons.md)   

