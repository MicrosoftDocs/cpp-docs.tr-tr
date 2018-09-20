---
title: Denetim gruplarını hizalama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], aligning
ms.assetid: a4f49a73-4a17-44b3-8568-aa35f646b5cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c791f2951eb7ac9947d48b563bde624bc3b7979f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46393587"
---
# <a name="aligning-groups-of-controls"></a>Denetim Gruplarını Hizalama

Aşağıdaki yordam, denetim gruplarını hizalama işlemini göstermektedir.

### <a name="to-align-groups-of-controls"></a>Denetim gruplarını hizalama

1. [Denetimleri seçin](../windows/selecting-multiple-controls.md) hizalamak istiyorsanız. Baskın denetimi olmasını istediğiniz denetim seçtiğinizden emin olun veya hizalama yürütme ya da komut boyutlandırma önce baskın denetimi olacak şekilde ayarlayın.

   Denetim grubunun son konumunu baskın denetimi konumuna bağlıdır. Baskın denetimi seçme hakkında daha fazla bilgi için bkz. [baskın denetimi belirtme](../windows/specifying-the-dominant-control.md).

2. Gelen **biçimi** menüsünde seçin **Hizala**ve ardından aşağıdaki hizalamaları birini seçin:

   - `Lefts`: Seçili denetimleri, sol kenarı boyunca hizalar.

   - `Centers`: Seçili denetimleri yatay olarak kendi center noktalarını boyunca hizalar.

   - `Rights`: Seçili denetimleri kendi sağ kenarı boyunca hizalar.

   - `Tops`: Seçili denetimleri üst kenarları boyunca hizalar.

   - `Middles`: seçilen denetimleri dikey olarak kendi orta noktaları boyunca hizalar.

   - `Bottoms`: Seçili denetimleri alt kenarları boyunca hizalar.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimlerin Düzenlenmesi](../windows/arrangement-of-controls-on-dialog-boxes.md)<br/>
[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)<br/>
[Denetimler](../mfc/controls-mfc.md)