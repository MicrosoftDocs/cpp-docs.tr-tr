---
title: "Cihaz bağlamları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OnPrepareDC method [MFC]
- windows [MFC], and device context
- drawing [MFC], device context
- CClientDC class [MFC], and GetDC method [MFC]
- drawing [MFC], in mouse and device contexts
- CDC class [MFC], objects
- device contexts [MFC]
- client areas
- CMetaFileDC class [MFC], and OnPrepareDC method [MFC]
- GDI objects [MFC], device contexts
- graphic objects [MFC], device contexts
- frame windows [MFC], device contexts
- metafiles and device contexts
- EndPaint method [MFC]
- printers [MFC], device contexts
- mouse [MFC], drawing and device contexts
- BeginPaint method, CPaintDC
- CPaintDC class [MFC], device context for painting
- windows [MFC], drawing directly into
- client areas, and device context
- device contexts [MFC], CDC class [MFC]
- user interface [MFC], device contexts
- device-independent drawing
- GetDC method and CClientDC class [MFC]
- CClientDC class [MFC], and ReleaseDC method [MFC]
- ReleaseDC method [MFC]
- device contexts [MFC], about device contexts
- drawing [MFC], directly into windows
- painting and device context
ms.assetid: d0cd51f1-f778-4c7e-bf50-d738d10433c7
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26d4a0e32a8b24a72447cf4227be128659316c0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="device-contexts"></a>Cihaz Bağlamları
Bir cihaz bağlamı bir görünüm veya yazıcı gibi bir aygıtı çizim öznitelikleri hakkında bilgi içeren bir Windows veri yapısıdır. Tüm çizim çağrılar çizim satırları, Şekil ve metinler için Windows API'larını yalıtan bir aygıt-context nesnesi aracılığıyla yapılır. Cihaz bağlamları CİHAZDAN bağımsız çizim Windows izin verir. Cihaz bağlamları ekran, yazıcı veya bir meta dosyası çizmek için kullanılabilir.  
  
 [CPaintDC](../mfc/reference/cpaintdc-class.md) nesneleri kapsülleyen çağırma pencerelerinin ortak deyim `BeginPaint` işlevi, cihaz bağlamında çizim, sonra çağırma `EndPaint` işlevi. `CPaintDC` Oluşturucu çağrıları `BeginPaint` siz ve yıkıcı çağrıları için `EndPaint`. Basitleştirilmiş işlem oluşturmaktır [CDC](../mfc/reference/cdc-class.md) nesnesi, çizme ve ardından destroy `CDC` nesnesi. Framework'te çok bile bu işlemi otomatik hale getirilmiştir. Özellikle, `OnDraw` işlevi geçirilir bir `CPaintDC` önceden hazırlanmış (aracılığıyla `OnPrepareDC`), ve yalnızca içine çizin. Çerçevesi tarafından yok ve arka plandaki cihaz bağlamı dönüş çağrısı sırasında Windows yayımlanır, `OnDraw` işlevi.  
  
 [CClientDC](../mfc/reference/cclientdc-class.md) nesneleri kapsülleyen bir pencere yalnızca istemci alanını temsil eden bir cihaz bağlamı ile çalışma. `CClientDC` Oluşturucu çağrıları `GetDC` işlevi ve yıkıcı çağrıları `ReleaseDC` işlevi. [CWindowDC](../mfc/reference/cwindowdc-class.md) nesneleri kapsülleyen çerçevesini dahil olmak üzere tüm pencereyi temsil eden bir cihaz bağlamı.  
  
 [CMetaFileDC](../mfc/reference/cmetafiledc-class.md) nesneleri çizim Windows Meta dosyası halinde yalıtma. Tersine için `CPaintDC` geçirilen `OnDraw`, bu durumda çağırmalısınız [OnPrepareDC](../mfc/reference/cview-class.md#onpreparedc) kendiniz.  
  
## <a name="mouse-drawing"></a>Fare çizim  
 Çoğu framework programında çizim — ve böylece çoğu cihaz bağlamı iş — görünümün içinde yapılır `OnDraw` üye işlevi. Bununla birlikte, cihaz bağlamı nesneleri başka bir amaçla kullanmaya devam edebilirsiniz. Örneğin, fare hareketini görünümünde izleme geri bildirim sağlamak için doğrudan görünüme beklemeden çizmek zorunda `OnDraw` çağrılabilir.  
  
 Böyle bir durumda kullanabileceğiniz bir [CClientDC](../mfc/reference/cclientdc-class.md) doğrudan görünüme çizmek için cihaz bağlam nesnesi.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Cihaz bağlamları (tanım)](http://msdn.microsoft.com/library/windows/desktop/dd183553)  
  
-   [Bir Görünümde Çizim Yapma](../mfc/drawing-in-a-view.md)  
  
-   [Bir Görünümü Kullanarak Kullanıcı Girişini Yorumlama](../mfc/interpreting-user-input-through-a-view.md)  
  
-   [Çizgiler ve eğrilerle](http://msdn.microsoft.com/library/windows/desktop/dd145028)  
  
-   [Doldurulmuş şekiller](http://msdn.microsoft.com/library/windows/desktop/dd162714)  
  
-   [Yazı tipleri ve metin](http://msdn.microsoft.com/library/windows/desktop/dd144819)  
  
-   [Renkleri](http://msdn.microsoft.com/library/windows/desktop/dd183450)  
  
-   [Koordinat alanları ve dönüştürmeler](http://msdn.microsoft.com/library/windows/desktop/dd183475)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pencere Nesneleri](../mfc/window-objects.md)

