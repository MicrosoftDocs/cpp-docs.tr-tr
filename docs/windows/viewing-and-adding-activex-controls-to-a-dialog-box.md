---
title: İletişim kutusuna ActiveX denetimleri ekleme ve görüntüleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.controls.activex
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding ActiveX controls
- Insert ActiveX Control command
- ActiveX controls [C++], adding to dialog boxes
ms.assetid: e1c2e3ae-e1b0-40d3-9766-623007073856
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ad663760efb5f969a7b7cf1b14d187b0382197b7
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643984"
---
# <a name="viewing-and-adding-activex-controls-to-a-dialog-box"></a>İletişim Kutusuna ActiveX Denetimleri Ekleme ve Görüntüleme
Visual Studio, iletişim kutusuna ActiveX denetimleri eklemenize olanak tanır.  
  
### <a name="to-see-the-activex-controls-you-have-available"></a>ActiveX denetimlerini görmek için elinizde  
  
1.  Bir iletişim kutusu, iletişim kutusu Düzenleyicisi'nde açın.  
  
2.  Sağ iletişim kutusunun gövdesinde herhangi bir yere tıklayın.  
  
3.  Kısayol menüsünde **ActiveX denetimi Ekle**.  
  
     [ActiveX denetimi Ekle iletişim kutusu](../windows/insert-activex-control-dialog-box.md) görünür, sisteminizdeki tüm ActiveX denetimlerini gösterme. ActiveX denetimi dosyasının yolu iletişim kutusunun en altında görünür.  
  
### <a name="to-add-an-activex-control-to-a-dialog-box"></a>İletişim kutusuna ActiveX denetimi eklemek için  
  
1.  İçinde [ActiveX denetimi Ekle iletişim kutusu](../windows/insert-activex-control-dialog-box.md), tıklatıp, iletişim kutusuna eklemek istediğiniz denetimi seçin **Tamam**.  
  
     Denetim, düzenlemek veya başka bir denetimde olduğu gibi işleyicileri için oluşturma iletişim kutusunda görüntülenir.  
  
    > [!NOTE]
    >  ActiveX denetimlerine ekleyebilirsiniz [araç penceresi](/visualstudio/ide/reference/toolbox). Daha fazla bilgi için [yönetmeye öğeler ve araç kutusu sekmeleri](http://msdn.microsoft.com/21285050-cadd-455a-b1f5-a2289a89c4db).  
  
    > [!CAUTION]
    >  ActiveX denetimleri, sisteminizdeki tüm dağıtmak için geçerli olmayabilir. Lütfen denetimleri yüklü yazılımlar için lisans sözleşmesi bakın veya yazılım şirketine başvurun.  
  
     Kolay erişim için araç kutusu penceresini denetimleri yerleştirebilirsiniz. Daha fazla bilgi için [özelleştirme araç kutusu iletişim kutusunda](http://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb).  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [MFC ActiveX denetimleri](../mfc/mfc-activex-controls.md)   
 [ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)