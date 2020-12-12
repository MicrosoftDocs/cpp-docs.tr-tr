---
description: 'Aşağıdakiler hakkında daha fazla bilgi edinin: özel durumlar: nesneleri özel durumlarda boşaltma'
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
ms.openlocfilehash: 47b10f3ecb96875ceee986eadda4595d2afbb77e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290563"
---
# <a name="exceptions-freeing-objects-in-exceptions"></a>Özel Durumlar: Özel Durumlarda Nesneleri Serbest Bırakma

Bu makalede, bir özel durum oluştuğunda nesneleri serbest bırakma yöntemi ve gereksinimi açıklanmaktadır. Konu başlıkları şunlardır:

- [Özel durumu yerel olarak işleme](#_core_handling_the_exception_locally)

- [Nesneleri yok etme sonrasında özel durumlar üretiliyor](#_core_throwing_exceptions_after_destroying_objects)

Çerçeve veya uygulama kesme normal program akışı tarafından oluşturulan özel durumlar. Bu nedenle, bir özel durumun oluşturulması durumunda bunları düzgün bir şekilde atabilirsiniz şekilde nesnelerin izlenmesini sürdürmek çok önemlidir.

Bunu yapmak için iki birincil yöntem vardır.

- Ve anahtar sözcüklerini kullanarak yerel özel durumları işleyin **`try`** ve **`catch`** sonra tüm nesneleri tek bir deyimle yok edin.

- **`catch`** Daha fazla işleme için özel durumu bloğunun dışına vermeden önce bloktaki tüm nesneleri yok edin.

Bu iki yaklaşım aşağıdaki sorunlu örnekteki çözümler olarak aşağıda gösterilmiştir:

[!code-cpp[NVC_MFCExceptions#14](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_1.cpp)]

Yukarıda yazıldığı gibi, `myPerson` tarafından bir özel durum oluşturulursa silinmeyecektir `SomeFunc` . Yürütme doğrudan bir sonraki dış özel durum işleyicisine atlar, normal işlev çıkışı atlanarak nesneyi silen kod. Özel durum işlevden ayrıldığında nesnenin işaretçisi kapsam dışına çıkar ve nesne tarafından kullanılan bellek, program çalıştığı sürece hiçbir zaman kurtarılmaz. Bu bir bellek sızıntısı; Bellek Tanılama kullanılarak algılanır.

## <a name="handling-the-exception-locally"></a><a name="_core_handling_the_exception_locally"></a> Özel durumu yerel olarak işleme

**Try/catch** paradigması, bellek sızıntılarını önlemeye ve özel durumlar oluştuğunda nesnelerinizin yok edilebilmesini sağlamak için savunma programlama yöntemi sağlar. Örneğin, bu makalenin önceki kısımlarında gösterilen örnek aşağıdaki gibi yeniden yazılabilir:

[!code-cpp[NVC_MFCExceptions#15](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_2.cpp)]

Bu yeni örnek, özel durumu yakalamak ve yerel olarak işlemek için bir özel durum işleyicisi ayarlar. Sonra işlevden normal olarak çıkar ve nesneyi yok eder. Bu örneğin önemli bir yönü, **try/catch** bloklarıyla özel durumu yakalamak için bir bağlam oluşturulur. Yerel bir özel durum çerçevesi olmadan, işlev bir özel durumun oluşturulmuş olduğunu hiçbir şekilde bilmez ve normal çıkma ve nesneyi yok etme şansınız olmaz.

## <a name="throwing-exceptions-after-destroying-objects"></a><a name="_core_throwing_exceptions_after_destroying_objects"></a> Nesneleri yok etme sonrasında özel durumlar üretiliyor

Özel durumları işlemenin bir diğer yolu da, bir sonraki dış özel durum işleme bağlamına geçirmektir. **`catch`** Blobundan sonra, yerel olarak ayrılan nesnelerinizi bazı temizleme işlemleri yapabilir ve daha fazla işlem için üzerinde özel durum oluşturabilirsiniz.

Oluşturma işlevinin yığın nesnelerini serbest bırakma gereksinimi olabilir veya olmayabilir. İşlev normal durumda döndürmeden önce yığın nesnesini her zaman ayırır, ayrıca işlev özel durumu oluşturmadan önce yığın nesnesini serbest bırakır. Diğer taraftan, işlev normal durumda döndürülmeden önce nesneyi serbest bırakılmadığı takdirde, yığın nesnesinin serbest bırakılıp bırakılmayacağı konusunda bir servis talebine karar vermelisiniz.

Aşağıdaki örnekte, yerel olarak ayrılan nesnelerin nasıl temizlenebileceğinden gösterilmektedir:

[!code-cpp[NVC_MFCExceptions#16](codesnippet/cpp/exceptions-freeing-objects-in-exceptions_3.cpp)]

Özel durum mekanizması çerçeve nesnelerini otomatik olarak ayırır; çerçeve nesnesinin yıkıcısı de çağrılır.

Özel durum oluşturabilecek işlevleri çağırırsanız, özel durumları yakaladığınızdan ve oluşturduğunuz tüm nesneleri yok etmek için bir şansına sahip olduğunuzdan emin olmak için **try/catch** bloklarını kullanabilirsiniz. Özellikle, birçok MFC işlevinin özel durum oluşturduğunu unutmayın.

Daha fazla bilgi için bkz. [özel durumlar: özel durumları yakalama ve silme](exceptions-catching-and-deleting-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
