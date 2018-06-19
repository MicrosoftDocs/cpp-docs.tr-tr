---
title: Yazdırma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- view classes [MFC], print operations
- documents [MFC], printing
- printing [MFC], from framework
- printing [MFC]
ms.assetid: be465e8d-b0c9-4fc5-9fa8-d10486064f76
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a7df782e3c30b9120fe7eb6728f1b622750d160f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33348243"
---
# <a name="printing"></a>Yazdırma
Microsoft Windows aygıt bağımsız görüntü uygular. MFC içinde aynı çizim çağrıları içinde buna `OnDraw` üye işlevi görünüm sınıfınızın çizim görüntüleme ve yazıcılar gibi diğer cihazları sorumlu. Baskı Önizleme için görüntülenecek benzetimli yazıcı çıktısından hedef aygıttır.  
  
##  <a name="_core_your_role_in_printing_vs.._the_framework.92.s_role"></a> Framework'ün rol karşılaştırması yazdırmada rolünüz  
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
 [{1&gt;Yazdırma ve yazdırma önizleme&lt;1}](../mfc/printing-and-print-preview.md)

