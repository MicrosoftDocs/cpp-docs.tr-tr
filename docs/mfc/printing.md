---
title: "Yazdırma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 48395276acfac71cd940be307c3b5f0735c356ca
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="printing"></a>Yazdırma
Microsoft Windows aygıt bağımsız görüntü uygular. MFC içinde aynı çizim çağrıları içinde buna `OnDraw` üye işlevi görünüm sınıfınızın çizim görüntüleme ve yazıcılar gibi diğer cihazları sorumlu. Baskı Önizleme için görüntülenecek benzetimli yazıcı çıktısından hedef aygıttır.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a>Framework'ün rol karşılaştırması yazdırmada rolünüz  
 Görünüm sınıfınıza aşağıdaki sorumlulukları vardır:  
  
-   Belgede kaç sayfalarıdır framework bildirin.  
  
-   Belirtilen bir sayfa yazdırmak için sorulduğunda, bu belgenin bölümünü çizin.  
  
-   Ayırma ve tüm yazı tiplerini veya yazdırma için gerekli diğer grafik cihaz arabirimi (GDI) kaynakları serbest bırakma.  
  
-   Gerekirse, herhangi bir gönderme çıkış kodları örneğin belirli bir sayfa yazdırma önce yazıcı modunu değiştirmek için sayfa başına temelinde Yazdırma yönünü değiştirmek için gerekli.  
  
 Framework'ün Sorumluluklar aşağıdaki gibidir:  
  
-   Görüntü **yazdırma** iletişim kutusu.  
  
-   Oluşturma bir [CDC](../mfc/reference/cdc-class.md) yazıcı nesnesi.  
  
-   Çağrı [StartDoc](../mfc/reference/cdc-class.md#startdoc) ve [EndDoc](../mfc/reference/cdc-class.md#enddoc) üye işlevlerini `CDC` nesnesi.  
  
-   Art arda çağrısı [StartPage](../mfc/reference/cdc-class.md#startpage) üye işlevini `CDC` nesnesi, görünüm sınıfı hangi sayfa yazdırılması ve çağırın bildirin [EndPage](../mfc/reference/cdc-class.md#endpage) üye işlevini `CDC` nesnesi.  
  
-   Geçersiz kılınabilir işlevler uygun zamanlarda görünümünde çağırın.  
  
 Aşağıdaki makaleler framework yazdırmayı ve baskı önizlemeyi nasıl destekler? ele alınmıştır:  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Varsayılan yazdırmayı yapma](../mfc/how-default-printing-is-done.md)  
  
-   [Birden çok belge](../mfc/multipage-documents.md)  
  
-   [Üstbilgiler ve altbilgiler](../mfc/headers-and-footers.md)  
  
-   [Yazdırma için GDI kaynaklarını ayırma](../mfc/allocating-gdi-resources.md)  
  
-   [Baskı Önizleme](../mfc/print-preview-architecture.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yazdırma ve Baskı Önizleme](../mfc/printing-and-print-preview.md)

