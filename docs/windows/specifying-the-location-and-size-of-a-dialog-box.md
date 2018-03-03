---
title: "İletişim kutusunun boyutunu ve konumunu belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03c4c6d6afb13a0e4ed8801838356ff0d1e851f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>İletişim Kutusunun Boyutunu ve Konumunu Belirtme
Bir iletişim kutusu yanı sıra konumu boyutunu ve bunun içinde denetimleri boyutunu ve konumunu iletişim birimler cinsinden ölçülür. Visual Studio durum seçtiğiniz zaman çubuğunda sağ alt köşesindeki değerlerini ayrı ayrı denetimler ve iletişim kutusu görünür.  
  
 Ayarlayabilirsiniz üç özellik [Özellikler penceresini](/visualstudio/ide/reference/properties-window) bir iletişim kutusu ekranda nerede görüneceğini belirtmek için. Boolean merkezi özelliğidir; değeri True olarak ayarlayın, iletişim kutusunun ekran Merkezi'nde her zaman görüntülenir. False olarak ayarlarsanız, ekran burada iletişim kutusu görünür açıkça tanımlamak için XPos ve YPos özelliklerini sonra ayarlayabilirsiniz. {X = 0, Y = 0} tanımlanan görüntüleme alanı sol üst köşesinin uzaklık değerleri konumu özelliklerdir. Konumu da dayanır **mutlak Hizala** özellik: değer doğru ise, koordinatları göre ekran; False ise, koordinatları iletişim sahibinin penceresi göreli olur.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](/dotnet/framework/resources/index) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimler](../mfc/controls-mfc.md)

