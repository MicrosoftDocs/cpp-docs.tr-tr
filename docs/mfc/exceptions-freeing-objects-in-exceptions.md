---
title: 'Özel durumlar: Özel durumlarda nesneleri serbest bırakma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- throwing exceptions [MFC], freeing objects in exceptions
- local exception handling
- memory leaks, caused by exception
- try-catch exception handling [MFC], destroying objects
- destroying objects [MFC]
- freeing objects [MFC]
- throwing exceptions [MFC], after destroying
- exception handling [MFC], destroying objects
ms.assetid: 3b14b4ee-e789-4ed2-b8e3-984950441d97
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21a63a55103cbefda2ba501c5609b772b2203166
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347834"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>Özel Durumlar: Özel Durumlarda Nesneleri Serbest Bırakma
Bu makalede, gereken ve bir özel durum oluştuğunda nesneleri serbest bırakma yöntemi açıklanmaktadır. Konular şunlardır:  
  
-   [Yerel olarak özel durum işleme](#_core_handling_the_exception_locally)  
  
-   [Nesneleri yok etme sonra özel durumları atma](#_core_throwing_exceptions_after_destroying_objects)  
  
 Framework veya uygulama kesme normal program akışınız tarafından oluşturulan özel durumları. Bu nedenle, böylece durumunda bir özel durum, düzgün şekilde bunları dispose nesneleri izlemenize çok önemlidir.  
  
 Bunu yapmak için başlıca iki yöntem vardır.  
  
-   Yerel olarak kullanarak özel durumları işleme **deneyin** ve **catch** anahtar sözcükler, ardından bir deyim ile tüm nesneler yok.  
  
-   Herhangi bir nesne destroy **catch** daha ayrıntılı işleme için blok dışında özel durum atma önce bloğu.  
  
 Bu iki yaklaşım, aşağıdaki sorunlu örnek çözümleri olarak aşağıda gösterilmiştir:  
  
 [!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]  
  
 Yukarıda yazıldığı şekilde `myPerson` tarafından bir özel durum oluşursa silinmez `SomeFunc`. Yürütme normal işlevi çıkış ve nesneyi siler kodu atlayarak doğrudan sonraki dış özel durum işleyici için atlar. Nesne işaretçisine kapsamının dışına işlev özel durum bırakır ve program çalışmadığı sürece nesnenin kapladığı bellek hiçbir zaman kurtarılacak gerekmesi. Bellek sızıntısı budur; Bellek Tanılama'yı kullanarak algılanabilmesi.  
  
##  <a name="_core_handling_the_exception_locally"></a> Yerel olarak özel durum işleme  
 **Try/catch** kip bellek sızıntılarını önleme ve özel durumları oluştuğunda nesnelerinizi yok sağlayarak bir savunma programlama yöntem sunar. Örneğin, bu makalenin önceki bölümlerinde gösterilen örnek gibi yazılması:  
  
 [!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]  
  
 Bu yeni örnek özel durumu yakalayın ve yerel olarak işlemek için bir özel durum işleyici ayarlar. İşlev normal olarak çıkar ve nesnesini yok eder. Önemli Bu örnek özel durumu yakalamak için bir bağlam ile kurulur yönüdür **try/catch** engeller. Yerel özel durum çerçeve işlev hiçbir zaman bir özel durum ve normalde çıkmak ve nesne yok etmek için Fırsat sahip olmaz anlarsınız.  
  
##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> Nesneleri yok etme sonra özel durumları atma  
 Özel durumları işlemek için başka bir yolu, bunları açın sonraki dış özel durum işleme bağlam geçirmektir. İçinde **catch** bloğu, yerel olarak ayrılmış nesnelerinin bazı temizleme yapın ve ardından başka bir işleme için özel durum.  
  
 Oluşturma işlevi olabilir veya yığın nesneleri serbest bırakma gerek kalmaz. Her zaman işlevi normal durumda döndürmeden önce yığın nesnesi kaldırır, ardından işlevi de yığın nesnesi özel durum atma önce ayırması. İşlev normalde nesne normal durumda döndürmeden önce ayırması değil, diğer yandan, ardından, bir olay temelinde yığın nesnesi serbest olup olmadığını karar vermeniz gerekir.  
  
 Yerel olarak nasıl ayrılmış nesneleri aşağıdaki örnekte gösterildiği Temizlenen:  
  
 [!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]  
  
 Özel durum mekanizması çerçeve nesneleri otomatik olarak kaldırır; çerçeve nesnesi yıkıcı olarak da bilinir.  
  
 Özel durumlar oluşturan işlevler çağırırsanız, kullanabileceğiniz **try/catch** bloğu özel durumları yakalar ve oluşturduğunuz nesneleri yok fırsatına sahip olduğundan emin olun. Özellikle, birçok MFC işlevi özel durumları atabilirsiniz unutmayın.  
  
 Daha fazla bilgi için bkz: [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

