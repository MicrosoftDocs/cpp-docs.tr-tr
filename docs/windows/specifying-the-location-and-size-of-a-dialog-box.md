---
title: Bir iletişim kutusu (C++) boyutunu ve konumunu belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [C++], size
- dialog boxes [C++], positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 854e4df84bfc5f75eda8f98fa117c199ba054b3a
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44316581"
---
# <a name="specifying-the-location-and-size-of-a-dialog-box-c"></a>Bir iletişim kutusu (C++) boyutunu ve konumunu belirtme

Bir C++ iletişim kutusu yanı sıra konumu boyutunu ve denetimleri içindeki boyutunu ve konumunu, iletişim kutusu birimleri cinsinden ölçülür. Visual Studio durum seçtiğiniz zaman çubuğunda sağ alt köşesindeki değerleri tek tek denetimler ve iletişim kutusu görünür.

İçinde ayarlayabilirsiniz üç özellik [Özellikler penceresi](/visualstudio/ide/reference/properties-window) bir iletişim kutusu ekran görüneceği yeri belirtmek için. **Merkezi** özelliğidir; Boole değeri ayarlamanız **True**, iletişim kutusunda her zaman ekranın ortasında görünür. Ayarlarsanız **False**, ardından ayarlayabilirsiniz **XPos** ve **YPos** ekranda olduğunda iletişim kutusu görünür açıkça tanımlamak için özellikleri. Sol üst köşesinde olarak tanımlanan görüntüleme alanının sapma değerlerini konumu özelliklerdir `{X=0, Y=0}`. Konumu de bağlıdır **mutlak hizalama** özelliği: varsa **True**, ekrana göreli; koordinatları, **False**, iletişim göreli koordinatları Sahibin penceresi.

Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[İletişim Kutularındaki Denetimler](../windows/controls-in-dialog-boxes.md)  
[Denetimler](../mfc/controls-mfc.md)