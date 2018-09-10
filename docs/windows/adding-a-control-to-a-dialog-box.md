---
title: Bir iletişim kutusu (C++) bir denetim ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.dialog
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], adding controls to
ms.assetid: b2a26d19-093f-49ca-93da-fef00dfbb381
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e60c64777ea4b5726721a267bcdd700cd71b4214
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44317907"
---
# <a name="adding-a-control-to-a-dialog-box-c"></a>Denetim ekleme iletişim kutusu (C++)

### <a name="to-add-a-control-to-a-dialog-box"></a>İletişim kutusuna denetim ekleme

1. Sekmeli pencere iletişim kutusu Düzenleyicisi çerçeveyi geçerli belgede olduğundan emin olun. Bir iletişim kutusu geçerli belgede değilse göremezsiniz **iletişim kutusu Düzenleyicisi sekmesi** içinde **araç kutusu**.

2. Üzerinde [iletişim kutusu Düzenleyicisi sekmesi](../windows/dialog-editor-tab-toolbox.md) , [araç penceresi](/visualstudio/ide/reference/toolbox), ardından istediğiniz denetimi seçin:

   - İletişim kutusu denetimi yerleştirmek istediğiniz konuma tıklayın. Denetim tıklattığınız görünür. Bilgi için [birden çok denetim ekleme](../windows/adding-multiple-controls.md).

       \- veya -

   - Sürükle ve bırak denetiminden **araç kutusu** pencere, iletişim kutusu konumuna. Daha fazla bilgi için [bir denetimi sırasında ekleme, boyutlandırma](../windows/sizing-a-control-while-you-add-it.md).

       \- veya -

   - Denetimde çift **araç kutusu** penceresi (iletişim kutusunda görünür) sonra denetim tercih ettiğiniz bir konuma yeniden konumlandırma.

Türleri üzerinde kullanılabilir denetimleri hakkında bilgi için **araç kutusu** penceresinde görmek [iletişim kutusu Düzenleyicisi sekmesi, araç penceresi](../windows/dialog-editor-tab-toolbox.md).

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
[İletişim Kutusu Denetimleri için Olay İşleyicileri Ekleme](../windows/adding-event-handlers-for-dialog-box-controls.md)  
[İletişim Kutusu Denetimleri ve Değişken Türleri](../ide/dialog-box-controls-and-variable-types.md)