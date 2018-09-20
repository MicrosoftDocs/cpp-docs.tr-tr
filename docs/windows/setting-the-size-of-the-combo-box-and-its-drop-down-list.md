---
title: Birleşik giriş kutusu ve aşağı açılan listesinin boyutunu ayarlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.combo
dev_langs:
- C++
helpviewer_keywords:
- combo boxes, sizing
- controls [C++], sizing
ms.assetid: 51fb53cf-9ddf-4a20-962e-8553938e55ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8bd2a81c10855dfe1d409b34612956616018dab7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413464"
---
# <a name="setting-the-size-of-the-combo-box-and-its-drop-down-list"></a>Birleşik Giriş Kutusu ve Aşağı Açılan Listesinin Boyutunu Ayarlama

İletişim kutusuna eklediğinizde bir birleşik giriş kutusu boyutlandırabilirsiniz. Aşağı açılan liste kutusunda boyutunu belirtebilirsiniz.

### <a name="to-size-a-combo-box"></a>Boyutuna bir birleşik giriş kutusu

1. Birleşik giriş kutusu denetimi sizin iletişim kutunuzda seçin.

   Başlangıçta, yalnızca sağ ve sol boyutlandırma tutamaçlarını etkindir.

2. Birleşik giriş kutusunun genişliğini ayarlamak için boyutlandırma tutamaçlarını kullanın.

Ayrıca, birleşik giriş kutusunun yanıdaki açılan kısmı dikey boyutunu ayarlayabilirsiniz.

#### <a name="to-set-the-size-of-the-combo-box-drop-down-list"></a>Aşağı açılan liste kutusunda açılan boyutunu ayarlamak için

1. Birleşik giriş kutusunun sağındaki açılan oku düğmeye tıklayın.

   ![Bir MFC projesinde bir birleşik giriş kutusu oku](../mfc/media/vccomboboxarrow.gif "vcComboBoxArrow")

   Genişletilmiş açılır listede alanı ile birleşik giriş kutusunun boyutunu göstermek için Denetim değişikliklerin anahattı.

2. Alt boyutlandırma tutamacı açılır listede alanın başlangıç boyutunu değiştirmek için kullanın.

   ![Birleşik giriş&#45;kutusu boyutlandırma MFC projesinde](../mfc/media/vccomboboxsizing.gif "vcComboBoxSizing")

3. Birleşik giriş kutusundaki açılır listede bölümünü yeniden kapatmak için açılan oka tıklayın.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Birleşik Giriş Kutusu Denetimine Değer Ekleme](../windows/adding-values-to-a-combo-box-control.md)<br/>
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)