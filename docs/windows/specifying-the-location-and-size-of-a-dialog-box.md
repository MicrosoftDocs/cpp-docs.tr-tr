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
ms.openlocfilehash: cc4c6867f5ed3791414619257fec33db4c632553
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890583"
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

