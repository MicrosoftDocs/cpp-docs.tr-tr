---
title: 'Özel Durumlar: Özel Durumlarda Nesneleri Serbest Bırakma'
ms.date: 11/04/2016
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
ms.openlocfilehash: 49c7c6b0481f90baa23609c1bb1596deda49f7bd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371995"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>Özel Durumlar: Özel Durumlarda Nesneleri Serbest Bırakma

Bu makalede, bir özel durum oluştuğunda nesneleri serbest etme gereksinimi ve yöntemi açıklanmaktadır. Konu başlıkları şunlardır:

- [Özel durum yerel olarak işleme](#_core_handling_the_exception_locally)

- [Nesneleri yok ettikten sonra özel durumlar atma](#_core_throwing_exceptions_after_destroying_objects)

Çerçeve veya uygulamanız tarafından atılan özel durumlar normal program akışını keser. Bu nedenle, bir özel durum atılırsa onları düzgün bir şekilde bertaraf böylece nesneleri yakından izlemek için çok önemlidir.

Bunu yapmak için iki birincil yöntem vardır.

- **Denemeler** ve anahtar kelimeleri **yakalamayı** kullanarak özel durumları yerel olarak ele alın ve ardından tüm nesneleri tek bir deyimle yok edin.

- Daha fazla kullanım için özel durumu bloğun dışına atmadan önce **catch** bloğundaki herhangi bir nesneyi yok edin.

Bu iki yaklaşım aşağıdaki sorunlu örneğe çözüm olarak aşağıda gösterilmiştir:

[!code-cpp[NVC_MFCExceptions#14](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

Yukarıda yazıldığı `myPerson` gibi, bir özel durum tarafından `SomeFunc`atılırsa silinmez. Yürütme, normal işlev çıkışını ve nesneyi silen kodu atlayarak doğrudan bir sonraki dış özel durum işleyicisine atlar. Özel durum işlevden ayrıldığında nesnenin işaretçisi kapsam dışına çıkar ve program çalıştığı sürece nesnenin kapattığı bellek asla kurtarılamayamaz. Bu bir bellek sızıntısı; bellek tanılama kullanılarak tespit edilecektir.

## <a name="handling-the-exception-locally"></a><a name="_core_handling_the_exception_locally"></a>Özel Durum'u Yerel Olarak Işleme

**Try/catch** paradigması, bellek sızıntılarını önlemek ve özel durumlar oluştuğunda nesnelerinizin yok edilmesini sağlamak için bir savunma programlama yöntemi sağlar. Örneğin, bu makalede daha önce gösterilen örnek aşağıdaki gibi yeniden yazılabilir:

[!code-cpp[NVC_MFCExceptions#15](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

Bu yeni örnek, özel durumu yakalamak ve yerel olarak işlemek için bir özel durum işleyicisi ayarlar. Daha sonra işlevi normal olarak çıkar ve nesneyi yok eder. Bu örneğin önemli yönü, özel durum yakalamak için bir bağlam **try/catch** blokları ile kurulmuş olmasıdır. Yerel bir özel durum çerçevesi olmadan, işlev bir özel durum atıldığını asla bilemez ve normal bir şekilde çıkıp nesneyi yok etme şansına sahip olmaz.

## <a name="throwing-exceptions-after-destroying-objects"></a><a name="_core_throwing_exceptions_after_destroying_objects"></a>Nesneleri Yok Ettikten Sonra Özel Durumlar Atma

Özel durumları işlemenin başka bir yolu da bunları bir sonraki dış özel durum işleme bağlamına aktarmaktır. **Yakalama** bloğunuzda, yerel olarak tahsis edilen nesnelerinizin biraz temizlenmesini yapabilir ve daha fazla işlem için özel durumu atabilirsiniz.

Atma işlevi yığın nesneleri dağıtmak için gerekebilir veya gerekmeyebilir. İşlev her zaman normal durumda dönmeden önce yığın nesnesi yer alıyorsa, o zaman işlev de özel durum atmadan önce yığın nesnesi üzerinde anlaşma gerekir. Diğer taraftan, işlev normal durumda dönmeden önce nesneyi normal olarak dağıtmıyorsa, yığın nesnesinin ayrılması gerekip gerekmediğine tek tek karar vermeniz gerekir.

Aşağıdaki örnek, yerel olarak ayrılan nesnelerin nasıl temizlenebileceğini gösterir:

[!code-cpp[NVC_MFCExceptions#16](../mfc/codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

Özel durum mekanizması çerçeve nesnelerini otomatik olarak yeralır; çerçeve nesnesinin yıkıcısı da denir.

Özel durumlar atabilen işlevleri çağırırsanız, özel durumları yakaladığından ve oluşturduğunuz nesneleri yok etme şansınız olduğundan emin olmak için **try/catch** bloklarını kullanabilirsiniz. Özellikle, birçok MFC işlevi özel durumlar atabilir unutmayın.

Daha fazla bilgi için özel [durumlar: Özel Durumları Yakalama ve Silme](../mfc/exceptions-catching-and-deleting-exceptions.md)bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
