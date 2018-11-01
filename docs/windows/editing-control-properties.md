---
title: Denetim Özelliklerini Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- controls [C++], undoing changes
- controls [C++], editing properties
- dialog box controls [C++], editing properties
ms.assetid: 9bdae21d-6dec-4344-a197-2ca4fc46d040
ms.openlocfilehash: cd9226e6eb4fc2b16d24cd0c9727d4fcbfdbf02b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50454814"
---
# <a name="editing-control-properties"></a>Denetim Özelliklerini Düzenleme

### <a name="to-edit-the-properties-of-a-control-or-controls"></a>Bir denetim veya denetimlerin özelliklerini düzenlemek için

1. İletişim kutusunda, değiştirmek istediğiniz denetimi seçin.

   > [!NOTE]
   > Birden çok denetim seçerseniz yalnızca seçili denetimleri ortak özelliklerini düzenleyebilirsiniz.

2. İçinde [Özellikler penceresi](/visualstudio/ide/reference/properties-window), denetim özelliklerini değiştirin.

   > [!NOTE]
   > Ayarladığınızda **bit eşlem** özelliği için bir düğme, radyo düğmesinin veya onay kutusu denetimi eşit **True**, bs_bıtmap denetim için uygulanan stili. Daha fazla bilgi için [düğme stilleri](../mfc/reference/styles-used-by-mfc.md#button-styles). Bir bit eşlem bir denetimle ilişkilendirme ilişkin bir örnek için bkz [CButton::SetBitmap](../mfc/reference/cbutton-class.md#setbitmap). Bit eşlemler içerikteyken denetiminizi görünmez **iletişim** Kaynak Düzenleyicisi.

### <a name="to-undo-changes-to-the-properties-of-a-control"></a>Bir denetimin özelliklerini değişiklikleri geri almak için

1. Denetim odağa sahip olduğundan emin olun **iletişim** Düzenleyici.

2. Seçin **geri** gelen **Düzenle** menü (odak denetimde değilse **geri** komutu kullanılamaz).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için bkz: [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [izlenecek yol: Windows formlarını yerelleştirme](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)