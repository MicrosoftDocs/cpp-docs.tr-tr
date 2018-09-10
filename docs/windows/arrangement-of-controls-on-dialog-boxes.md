---
title: Denetimlerin düzenlenmesi iletişim kutuları (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], positioning
- dialog box controls [C++], placement
- Dialog Editor [C++], arranging controls
ms.assetid: 832491cf-98af-42e5-a854-2cb135fd45c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 46bc2d627c9efbb49227e17c809d188aa3a8b5fc
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44315242"
---
# <a name="arrangement-of-controls-on-dialog-box-ces"></a>İletişim kutusundaki denetimlerin kutu es (C++)

**İletişim** Düzenleyicisi, hizalama ve denetimleri boyut otomatik düzeni araçlar sağlar. Çoğu görevler için kullanabileceğiniz [iletişim kutusu araç çubuğunu](../windows/showing-or-hiding-the-dialog-editor-toolbar.md). Tüm **iletişim kutusu Düzenleyicisi** araç çubuğu komutlarını kullanılabilir ayrıca **biçimi** menü ve çoğu [kısayol tuşları](../windows/accelerator-keys-for-the-dialog-editor.md).

İletişim kutuları için Düzen komutların çoğu yalnızca birden fazla denetim seçildiğinde kullanılabilir. Tek bir denetim veya birden çok denetim seçin ve birden fazla denetim seçildiğinde, seçtiğiniz birinci varsayılan olarak "baskın" denetimidir. Denetimleri ve baskın denetimi seçme hakkında daha fazla bilgi için bkz: [seçerek denetimleri](../windows/selecting-controls.md).

Konum, yükseklik ve genişlik geçerli denetimin durum çubuğunun sağ alt köşesinde görüntülenir. Tüm iletişim kutusu seçildiğinde durum çubuğunda bir bütün ve yüksekliğini ve genişliğini iletişim kutusunun konumunu görüntüler.

- [İletişim Kutusu Düzenleyicisi Durumları (Kılavuzlar ve Izgaralar)](../windows/dialog-editor-states-guides-and-grids.md)

- [İletişim Kutusundaki Radyo Düğmelerini Gruplama](../windows/grouping-radio-buttons-on-a-dialog-box.md)

- [Denetim Gruplarını Hizalama](../windows/aligning-groups-of-controls.md)

- [Denetimler Arasındaki Boşlukları Eşitleme](../windows/evening-the-spacing-between-controls.md)

- [İletişim Kutusunda Denetimleri Ortalama](../windows/centering-controls-in-a-dialog-box.md)

- [Basma Düğmelerini İletişim Kutusunun Sağında veya Altında Düzenleme](../windows/arranging-push-buttons-along-the-right-or-bottom-of-a-dialog-box.md)

- [Denetimlerin Sekme Sırasını Değiştirme](../windows/changing-the-tab-order-of-controls.md)

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
[Denetimler](../mfc/controls-mfc.md)