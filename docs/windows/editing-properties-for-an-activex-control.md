---
title: Bir ActiveX denetimi özelliklerini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], editing properties
- ActiveX controls [C++], properties
ms.assetid: e5880c62-36c7-4701-bc99-97a82974c22a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6c1db7390be47d2f9530708b2a4cd59dd1c22cc7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610400"
---
# <a name="editing-properties-for-an-activex-control"></a>ActiveX Denetimi Özelliklerini Düzenleme

ActiveX denetimleri bağımsız satıcıları tarafından sağlanan kendi özellikleri ve özellikleri ile donatıldı gelebilir. ActiveX denetimleri için özellikleri görüntülenir **özellikleri** penceresi. ActiveX denetiminin yazarlar tarafından oluşturulan tüm özellik sayfaları ek olarak, görüntülenen **özellikler sayfaları** iletişim kutusu (görüntülemek için **özellik sayfası** belirlibirActiveXdenetimiiçintıklayın **Özellik sayfası** düğmesine [Özellikler penceresi](/visualstudio/ide/reference/properties-window)).

Çeşitli sekmelere ActiveX denetiminin bir parçası olarak gelen özellik sayfalarını bağlı olarak bir ActiveX denetimi için özellik sayfası görüntülenir.

> [!NOTE]
> Aşağıdaki yordam, özellik sayfasını kullanarak ActiveX denetimlerini düzenlemek için geçerlidir. Ayrıca göz atabilir ve ActiveX özellikleri yeni Düzenle **özellikleri** penceresi.

### <a name="to-edit-properties-for-an-activex-control"></a>ActiveX denetimi özelliklerini düzenlemek için

1. Seçin **ActiveX** denetimi.

2. Üzerinde **görünümü** menüsünde tıklatın **özellik sayfası** ve özelliklerini görüntüleyin.

3. Özellik sayfasında gerekli değişiklikleri yapın.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusuna ActiveX Denetimleri Ekleme ve Görüntüleme](../windows/viewing-and-adding-activex-controls-to-a-dialog-box.md)  
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)  
[ActiveX Denetim Kapsayıcıları](../mfc/activex-control-containers.md)