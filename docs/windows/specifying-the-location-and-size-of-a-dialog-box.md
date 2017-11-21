---
title: "İletişim kutusunun boyutunu ve konumunu belirtme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog boxes, size
- dialog boxes, positioning
ms.assetid: 2b7c495e-6595-4cfb-9664-80b2826d0851
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0dcd2acc4067e62d5cc44ca4e180f591e9fe63b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="specifying-the-location-and-size-of-a-dialog-box"></a>İletişim Kutusunun Boyutunu ve Konumunu Belirtme
Bir iletişim kutusu yanı sıra konumu boyutunu ve bunun içinde denetimleri boyutunu ve konumunu iletişim birimler cinsinden ölçülür. Visual Studio durum seçtiğiniz zaman çubuğunda sağ alt köşesindeki değerlerini ayrı ayrı denetimler ve iletişim kutusu görünür.  
  
 Ayarlayabilirsiniz üç özellik [Özellikler penceresini](/visualstudio/ide/reference/properties-window) bir iletişim kutusu ekranda nerede görüneceğini belirtmek için. Boolean merkezi özelliğidir; değeri True olarak ayarlayın, iletişim kutusunun ekran Merkezi'nde her zaman görüntülenir. False olarak ayarlarsanız, ekran burada iletişim kutusu görünür açıkça tanımlamak için XPos ve YPos özelliklerini sonra ayarlayabilirsiniz. {X = 0, Y = 0} tanımlanan görüntüleme alanı sol üst köşesinin uzaklık değerleri konumu özelliklerdir. Konumu da dayanır **mutlak Hizala** özellik: değer doğru ise, koordinatları göre ekran; False ise, koordinatları iletişim sahibinin penceresi göreli olur.  
  
 Kaynakları yönetilen projelerine ekleme hakkında daha fazla bilgi için lütfen bkz [masaüstü uygulamalarında kaynakları](https://msdn.microsoft.com/library/f45fce5x.aspx) içinde *.NET Framework Geliştirici Kılavuzu.* Kaynak dosyaları el ile yönetilen projelerine ekleme, kaynaklara erişme, statik kaynaklarını görüntüleme ve özellikleri için kaynak dizeleri atama hakkında daha fazla bilgi için bkz: [Masaüstü uygulamaları için kaynak dosyalar oluşturma](https://msdn.microsoft.com/library/xbx3z216.aspx). Genelleştirme ve yerelleştirme kaynakların yönetilen uygulamalar hakkında daha fazla bilgi için bkz: [Globalizing ve .NET Framework uygulamaları yerelleştirme](https://msdn.microsoft.com/library/h6270d0z.aspx).  
  
## <a name="requirements"></a>Gereksinimler  
 Win32  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İletişim kutularındaki denetimler](../windows/controls-in-dialog-boxes.md)   
 [Denetimleri](../mfc/controls-mfc.md)

