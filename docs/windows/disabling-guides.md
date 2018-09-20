---
title: Kılavuzları devre dışı bırakma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- guides, disabling snapping
- Dialog editor [C++], snap to guides
- snap to guides (Dialog editor)
- controls [C++], snap to guides/grid
ms.assetid: 51efa07b-8684-474e-a0b4-191ec5d91d1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35c552a6bb384f87c358ba25a945a7f02cc30114
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380808"
---
# <a name="disabling-guides"></a>Kılavuzları Devre Dışı Bırakma

Özel anahtarları Yaslanma etkisini kılavuzları devre dışı bırakmak için fare ile birlikte kullanabilirsiniz. Kullanarak **Alt** anahtarı, seçilen Kılavuzu Yaslanma etkilerini devre dışı bırakır. Taşıma Kılavuzu ile **Shift** anahtar yaslanan denetimlerin kılavuzla taşınmasını engeller.

### <a name="to-disable-the-snapping-effect-of-the-guides"></a>Yaslanma etkisini kılavuzları devre dışı bırakmak için

1. Tutarken denetimi sürükleyin **Alt** anahtarı.

### <a name="to-move-guides-without-moving-the-snapped-controls"></a>Yaslanan denetimlerin taşımadan kılavuzları taşımak için

1. Tutarken kılavuzu sürükleyin **Shift** anahtarı.

### <a name="to-turn-off-the-guides"></a>Kılavuzları için

1. Gelen **biçimi** menüsünde seçin **Kılavuz ayarları**.

2. İçinde [kılavuz Ayarları iletişim kutusu](../windows/guide-settings-dialog-box.md)altında **düzeni kılavuzları**seçin **hiçbiri**.

   > [!NOTE]
   > Ayrıca cetvel çubuğuna erişmek için çift **Kılavuz ayarları** iletişim kutusu.

\- veya -

- Üzerinde **biçimi** menüsünü tıklatın **rehberi Aç/Kapat**.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutusu Düzenleyicisi Durumları (Kılavuzlar ve Izgaralar)](../windows/dialog-editor-states-guides-and-grids.md)<br/>
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)