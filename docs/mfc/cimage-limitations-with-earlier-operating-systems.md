---
title: "Önceki işletim sistemlerinde Cımage sınırlamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CImage
dev_langs: C++
helpviewer_keywords: CImage class [MFC], limitations
ms.assetid: 4bedaab8-7dd1-4c91-ab35-b75fb56765b0
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb13e31df1b30c775d1e961f09b10163d06b1ea7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cimage-limitations-with-earlier-operating-systems"></a>Önceki İşletim Sistemlerinde CImage Sınırlamaları
Birçok `CImage` işlevleri yalnızca Windows daha yeni sürümleri ile çalışır: Windows 95/98 veya Windows NT 4.0 veya Windows 2000. Bu makalede belirli yöntemlerini sürüm sınırlamaları açıklanmaktadır.  
  
 [CImage::PlgBlt](../atl-mfc-shared/reference/cimage-class.md#plgblt) ve [CImage::MaskBlt](../atl-mfc-shared/reference/cimage-class.md#maskblt) iş yalnızca Windows NT 4.0 veya üstü. Windows 95/98 veya sonraki sürümlerde çalışan uygulamalar üzerinde çalışmaz.  
  
 [CImage::AlphaBlend](../atl-mfc-shared/reference/cimage-class.md#alphablend) ve [CImage::TransparentBlt](../atl-mfc-shared/reference/cimage-class.md#transparentblt) yalnızca Windows 2000 veya üstü ve Windows 98 ile çalışmak ya da bu yöntemleri kullanmak için msimg32.lib ile bağlamanız gerekir çünkü daha sonra. (Yalnızca Windows 2000 veya üstü ve Windows 98 çalışan uygulamalara veya daha sonra bu kitaplık kullanılabilir.)  
  
 Dahil edebileceğiniz `AlphaBlend` ve `TransparentBlt` uygulamada yalnızca bu yöntemleri hiçbir zaman çağrılmadığı varsa, Windows 95 veya Windows NT 4.0 üzerinde çalışır. Uygulamanız bu yöntemleri içerir ve önceki işletim sistemlerinde çalışan gerekir, bağlayıcı 's kullanmalısınız [/delayload](../build/reference/delayload-delay-load-import.md) msimg32.lib yüklenmesini geciktirmek için. Uygulamanızı Windows NT 4.0 veya Windows 95 altında çalışırken aşağıdaki yöntemlerden birini çağırmaz sürece msimg32.lib yüklemek çalışmaz. Kullanılıp denetleyebilirsiniz saydamlık desteği olan kullanılabilir kullanarak `CImage::IsTransparencySupported` yöntemi.  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCDocViewSDI#8](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_1.cpp)]  
  
 Bu yöntemlerini çağıran bir uygulama derlemek için INSERT bir # _WIN32_WINNT define önce # Windows sürümüne eşit veya bundan büyük 5.0 olduğunu belirten bir sistem üstbilgiler including:  
  
 [!code-cpp[NVC_MFCDocViewSDI#9](../mfc/codesnippet/cpp/cimage-limitations-with-earlier-operating-systems_2.h)]  
  
 Uygulamanızı Windows 2000 veya Windows 98 eski bir işletim sisteminde çalıştırmak gerekmez, kullanmadan doğrudan msimg32.lib bağlayabilirsiniz **/delayload**.  
  
 [CImage::Draw](../atl-mfc-shared/reference/cimage-class.md#draw) Windows NT 4.0 veya Windows 95 makinelerinden Windows 2000 ve Windows 98 ile kullanıldığında farklı şekilde davranır.  
  
 Uygulamanıza _WIN32_WINNT kümesiyle 0x0500,'den küçük bir değer derleme yaparsanız **çizin** iş, ancak otomatik olarak Windows 2000 ve Windows 98 ve üzerini çalıştıran sistemlerde saydamlık işleyecek değil.  
  
 Sizin için 0x0500 ayarlamak _WIN32_WINNT uygulama ya da daha derleme yaparsanız **çizin** saydamlık otomatik olarak Windows 2000 veya Windows 98 ve üzerini çalıştıran sistemlerde işleyecek. Ayrıca çalışır, ancak Windows NT 4.0 ve Windows 95; saydamlık desteği Ancak, kullanmalıdır **/delayload** msimg32 yüklenmesini geciktirmek için. İçin yukarıda açıklandığı gibi LIB `AlphaBlend` ve `TransparentBlt`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cımage sınıfı](../atl-mfc-shared/reference/cimage-class.md)
