---
title: İletişim kutusunun boyutunu ve konumunu belirtme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3a3a9a629ec138659a7b0d2aba2460aced31fc74
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649009"
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>İletişim Kutusunun Boyutunu ve Konumunu Belirtme
Bir iletişim kutusu yanı sıra konumu boyutunu ve denetimleri içindeki boyutunu ve konumunu, iletişim kutusu birimleri cinsinden ölçülür. Visual Studio durum seçtiğiniz zaman çubuğunda sağ alt köşesindeki değerleri tek tek denetimler ve iletişim kutusu görünür.  
  
 İçinde ayarlayabilirsiniz üç özellik [Özellikler penceresi](/visualstudio/ide/reference/properties-window) bir iletişim kutusu ekran görüneceği yeri belirtmek için. Boolean merkezi özelliğidir; değeri True olarak ayarlayın, iletişim kutusunda her zaman ekranın ortasında görünür. False olarak ayarlayın, ardından ekranda olduğunda iletişim kutusu görünür açıkça tanımlamak için XPos ve YPos özellikleri ayarlayabilirsiniz. Konumu sol üst köşesinde {X = 0 olarak, Y = 0} tanımlandığında görüntüleme alanının sapma değerlerini özelliklerdir. Konumu de bağlıdır **mutlak hizalama** özelliği: True ise kutusunun ekrana göreli koordinatları; False ise, iletişim sahibinin penceresiyle ilişkili koordinatları.  
  
 Yönetilen projelere kaynak ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakların](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu*. Kaynak dosyalarını yönetilen projelere el ile ekleme, kaynaklara erişme, statik kaynakları görüntüleme ve kaynak dizelerini özelliklere atama hakkında daha fazla bilgi için bkz: [Creating Resource Files Masaüstü uygulamaları için](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamalarını yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimler](../mfc/controls-mfc.md)