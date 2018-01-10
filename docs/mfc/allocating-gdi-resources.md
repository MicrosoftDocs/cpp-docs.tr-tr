---
title: "GDI kaynaklarını ayırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7420dbdc1f7560eae9bc5b1a15954c3d68b59678
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="allocating-gdi-resources"></a>GDI Kaynaklarını Ayırma
Bu makalede, ayırmak ve yazdırma için gerekli Windows grafik cihaz arabirimi (GDI) nesneleri serbest bırakma açıklanmaktadır.  
  
> [!NOTE]
>  GDI + ile Windows XP dahil edilmiştir ve Windows NT 4.0 SP6, Windows 2000, Windows 98 ve Windows Me için yeniden dağıtılabilir olarak kullanılabilir En son yeniden yüklemek için bkz [http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm](http://www.microsoft.com/msdownload/platformsdk/sdkupdate/psdkredist.htm). Daha fazla bilgi için GDI + SDK belgelerine bakın: [http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Belirli yazı tiplerini, kalemler veya diğer GDI nesneleri yazdırma için ancak ekran görüntüsü için kullanılacak gerektiğini varsayalım. Gereksinim duydukları bellek nedeniyle, uygulama başlatıldığında bu nesneler ayırmak için yetersiz olduğunu. Uygulama bir belge yazdırılırken değil, bu bellek diğer amaçlar için gerekebilir. Yazdırma işlemi başladığında, bunları ayırmak ve bunları uçları yazdırırken silmek iyidir.  
  
 Bu GDI nesneleri ayırmak için geçersiz kılma [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) üye işlevi. Bu işlev iki nedenden dolayı bu amaç için uygundur: framework bu işlev bir kez her yazdırma işinin ve aksine başında çağırması [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), bu işlev erişimi [CDC](../mfc/reference/cdc-class.md) Yazıcı aygıt sürücüsü temsil eden nesne. Görünüm sınıfınızda GDI nesneleri işaret üye değişkenleri tanımlama yazdırma işi sırasında kullanmak için bu nesneleri depolayabilirsiniz (örneğin, **CFont \***  üyeler vb.).  
  
 Oluşturduğunuz GDI nesneleri kullanmak için bunları yazıcı cihaz bağlamında içine seçin [OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevi. Belgenin farklı sayfaları için farklı GDI nesneleri gerekiyorsa, inceleyebilirsiniz `m_nCurPage` üyesi [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı ve buna göre GDI nesnesi seçin. GDI nesnesi birkaç ardışık sayfalar için gerekiyorsa, Windows, bu cihaz bağlamına her zaman seçmenizi gerektirir `OnPrint` olarak adlandırılır.  
  
 Bu GDI nesneleri serbest bırakma için geçersiz kılın [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) üye işlevi. Framework'te diğer görevlere uygulama döndürmeden önce yazdırma özgü GDI nesneleri serbest bırakma fırsatı verir her bir yazdırma işinin sonunda bu işlevi çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma](../mfc/printing.md)   
 [Varsayılan Yazdırmayı Yapma](../mfc/how-default-printing-is-done.md)

