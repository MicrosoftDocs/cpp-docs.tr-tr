---
title: Denetim özelliklerini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls, editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bc7b555ee04b8739040e0ec9d53c3820c2e13f16
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648752"
---
# <a name="editing-control-properties"></a>Denetim Özelliklerini Düzenleme
### <a name="to-edit-the-properties-of-a-control-or-controls"></a>Bir denetim veya denetimlerin özelliklerini düzenlemek için  
  
1.  İletişim kutusunda, değiştirmek istediğiniz denetimi seçin.  
  
    > [!NOTE]
    >  Birden çok denetim seçerseniz yalnızca seçili denetimleri ortak özelliklerini düzenleyebilirsiniz.  
  
2.  İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), denetim özelliklerini değiştirin.  
  
    > [!NOTE]
    >  Ayarladığınızda **bit eşlem** özelliği için bir düğme, radyo düğmesinin veya onay kutusu denetimi eşit **True**, bs_bıtmap denetim için uygulanan stili. Daha fazla bilgi için [düğme stilleri](../mfc/reference/styles-used-by-mfc.md#button-styles). Bir bit eşlem bir denetimle ilişkilendirme ilişkin bir örnek için bkz [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Bit eşlemler içerikteyken denetiminizi görünmez **iletişim** Kaynak Düzenleyicisi.  
  
### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Bir denetimin özelliklerini değişiklikleri geri almak için  
  
1.  Denetim odağa sahip olduğundan emin olun **iletişim** Düzenleyici.  
  
2.  Seçin **geri** gelen **Düzenle** menü (odak denetimde değilse **geri** komutu kullanılamaz).  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) ve [İzlenecek yol: ASP.NET ile yerelleştirme için kaynakların kullanarak](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)