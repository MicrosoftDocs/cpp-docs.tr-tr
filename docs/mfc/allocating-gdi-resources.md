---
title: GDI kaynaklarını ayırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resources [MFC], printing
- GDI objects [MFC], allocating during printing
- printing [MFC], allocating GDI resources
ms.assetid: cef7e94d-5a27-4aea-a9ee-8369fc895d3a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25f05c29c74756276cdf3fd1f88048b9a5b87fa7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343227"
---
# <a name="allocating-gdi-resources"></a>GDI Kaynaklarını Ayırma
Bu makalede, ayırmak ve yazdırma için gerekli Windows grafik cihaz arabirimi (GDI) nesneleri serbest bırakma açıklanmaktadır.  
  
> [!NOTE]
>  Daha fazla bilgi için GDI + SDK belgelerine bakın: [ http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/GDIPlus/GDIPlus.asp ](http://msdn.microsoft.com/library/default.aspurl=/library/gdicpp/gdiplus/gdiplus.asp).  
  
 Belirli yazı tiplerini, kalemler veya diğer GDI nesneleri yazdırma için ancak ekran görüntüsü için kullanılacak gerektiğini varsayalım. Gereksinim duydukları bellek nedeniyle, uygulama başlatıldığında bu nesneler ayırmak için yetersiz olduğunu. Uygulama bir belge yazdırılırken değil, bu bellek diğer amaçlar için gerekebilir. Yazdırma işlemi başladığında, bunları ayırmak ve bunları uçları yazdırırken silmek iyidir.  
  
 Bu GDI nesneleri ayırmak için geçersiz kılma [OnBeginPrinting](../mfc/reference/cview-class.md#onbeginprinting) üye işlevi. Bu işlev iki nedenden dolayı bu amaç için uygundur: framework bu işlev bir kez her yazdırma işinin ve aksine başında çağırması [OnPreparePrinting](../mfc/reference/cview-class.md#onprepareprinting), bu işlev erişimi [CDC](../mfc/reference/cdc-class.md) Yazıcı aygıt sürücüsü temsil eden nesne. Görünüm sınıfınızda GDI nesneleri işaret üye değişkenleri tanımlama yazdırma işi sırasında kullanmak için bu nesneleri depolayabilirsiniz (örneğin, **CFont \***  üyeler vb.).  
  
 Oluşturduğunuz GDI nesneleri kullanmak için bunları yazıcı cihaz bağlamında içine seçin [OnPrint](../mfc/reference/cview-class.md#onprint) üye işlevi. Belgenin farklı sayfaları için farklı GDI nesneleri gerekiyorsa, inceleyebilirsiniz `m_nCurPage` üyesi [Cprintınfo](../mfc/reference/cprintinfo-structure.md) yapısı ve buna göre GDI nesnesi seçin. GDI nesnesi birkaç ardışık sayfalar için gerekiyorsa, Windows, bu cihaz bağlamına her zaman seçmenizi gerektirir `OnPrint` olarak adlandırılır.  
  
 Bu GDI nesneleri serbest bırakma için geçersiz kılın [OnEndPrinting](../mfc/reference/cview-class.md#onendprinting) üye işlevi. Framework'te diğer görevlere uygulama döndürmeden önce yazdırma özgü GDI nesneleri serbest bırakma fırsatı verir her bir yazdırma işinin sonunda bu işlevi çağırır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma](../mfc/printing.md)   
 [Varsayılan Yazdırmayı Yapma](../mfc/how-default-printing-is-done.md)

