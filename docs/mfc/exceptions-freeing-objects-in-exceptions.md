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
ms.openlocfilehash: f0f7c9c28e438ad9d5cf643f005175512192be80
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390779"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>Özel Durumlar: Özel Durumlarda Nesneleri Serbest Bırakma

Bu makalede, gereksinim ve bir özel durum oluştuğunda nesneleri serbest bırakma yöntemi açıklanmaktadır. Konular şunlardır:

- [Yerel olarak özel durum işleme](#_core_handling_the_exception_locally)

- [Nesnelerini yok etme sonra özel durumları atma](#_core_throwing_exceptions_after_destroying_objects)

Framework tarafından veya uygulama kesme normal program akışınız tarafından oluşturulan bir özel durumlar. Bu nedenle, bir özel durum durumunda, düzgün bir şekilde bunları dispose, böylece nesneleri izlemenize çok önemlidir.

Bunu yapmak için iki birincil yöntem vardır.

- Yerel olarak kullanarak özel durumları işlemek **deneyin** ve **catch** anahtar sözcükler, ardından bir ifade ile tüm nesneler yok.

- Herhangi bir nesneyi yok etmek **catch** önce daha fazla işleme için bloğun dışından özel durumu oluşturan blok.

Bu iki yaklaşımı, sorunlu aşağıdaki örneğe çözümleri olarak aşağıda gösterilmiştir:

[!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

Yukarıda yazıldığı gibi `myPerson` tarafından bir özel durum oluşturulursa silinmeyecek `SomeFunc`. Yürütme normal işlev çıkışı ve nesneyi siler kodu atlayarak doğrudan sonraki dıştaki özel durum işleyicisine atlar. Nesne işaretçisi, işlev özel durum bırakır ve nesne tarafından kullanılan bellek, program çalışırken sürece hiçbir zaman kurtarılır kapsam dışına gider. Bu, bir bellek sızıntısı, Bellek Tanılama'yı kullanarak algılanır.

##  <a name="_core_handling_the_exception_locally"></a> Yerel olarak özel durum işleme

**Try/catch** paradigma bellek sızıntılarını önleme ve özel durumları oluştuğunda nesnelerinizi edilir sağlamaya yönelik bir savunma programlama yöntemi sağlar. Örneğin, bu makalenin önceki bölümlerinde gösterilen örnekte şu şekilde yazılması:

[!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

Bu yeni örnek özel durumu yakalar ve bunu yerel olarak işlemek için bir özel durum işleyicisi ayarlar. İşlev normal olarak çıkar ve nesnesini yok eder. Bu örnek önemli yönüyle istisna yakalamak için bir bağlam ile kurulur olan **try/catch** engeller. Bir yerel özel durum çerçeve işlev hiçbir zaman bir özel durum ve normalde çıkmak ve nesneyi yok etmek için bir fırsat yok anlarsınız.

##  <a name="_core_throwing_exceptions_after_destroying_objects"></a> Nesnelerini yok etme sonra özel durumları atma

Özel durumları işlemek için başka bir yolu, bunları sonraki dıştaki özel durum işleme bağlam açın geçirmektir. İçinde **catch** bloğu, yerel olarak ayrılan nesnelerin biraz temizlik yapmak ve sonra daha ayrıntılı işleme için özel durum.

Oluşturma işlevi veya yığın nesnelerini ayırması gerekmeyebilir. İşlev her zaman yığın nesnesi normal durumda döndürmeden önce serbest bırakır, ardından işlevi de yığın nesnesi özel durum önce serbest. İşlev normalde nesne normal durumda döndürmeden önce serbest değil, diğer taraftan, daha sonra bir olay temelinde yığın nesnesi serbest olup olmadığını karar vermeniz gerekir.

Aşağıdaki örnekte gösterildiği nasıl yerel olarak ayrılmış nesnelerin Temizlenen:

[!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

Özel durum mekanizması, çerçeve nesneleri otomatik olarak kaldırır; Çerçeve nesnenin yok Edicisi olarak da adlandırılır.

Özel durumlar oluşturabilecek bir işlev çağırırsanız, kullanabileceğiniz **try/catch** bloğunun özel durumları yakalama ve oluşturduğunuz herhangi bir nesne yok etme olanağına sahip olduğundan emin olun. Özellikle, birçok MFC işlevi özel durumlar oluşturabilecek dikkat edin.

Daha fazla bilgi için [özel durumlar: çalýþýrçalýþma yakalama ve silme özel durumları](../mfc/exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

