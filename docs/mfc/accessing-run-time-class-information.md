---
title: Çalışma Süresi Sınıf Bilgilerine Erişme
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], and RTTI
- CObject class [MFC], using IsKindOf method [MFC]
- run time [MFC], class information
- RUNTIME_CLASS macro [MFC]
- CObject class [MFC], using RUNTIME_CLASS macro [MFC]
- RTTI compiler option [MFC]
- CObject class [MFC], accessing run-time class information
- run time [MFC]
- IsKindOf method method [MFC]
- run-time class [MFC], accessing information
- classes [MFC], run-time class information
- run-time class [MFC]
- RUNTIME_CLASS macro, using
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
ms.openlocfilehash: 4a836bb7bd03bd6654e5c940442fecf541042fd1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354222"
---
# <a name="accessing-run-time-class-information"></a>Çalışma Süresi Sınıf Bilgilerine Erişme

Bu makalede, çalışma zamanında bir nesnenin sınıfı hakkında bilgilere nasıl erişilen açıklar.

> [!NOTE]
> MFC, Visual C++ 4.0'da tanıtılan [Run-Time Type Information](../cpp/run-time-type-information.md) (RTTI) desteğini kullanmaz.

Sınıfınızı CObject'ten türetdiyseniz ve**DYNAMIC** `IMPLEMENT_DYNAMIC` `DECLARE_DYNCREATE` `IMPLEMENT_DYNCREATE` `DECLARE_SERIAL` `IMPLEMENT_SERIAL` `CObject` [CObject'ten Bir Sınıf Türetilmiş](../mfc/deriving-a-class-from-cobject.md)makalede açıklanan **DECLARE**_ DYNAMIC ve , and , veya makroları kullandıysanız, sınıf çalışma zamanında bir nesnenin tam sınıfını belirleme yeteneğine sahiptir. [CObject](../mfc/reference/cobject-class.md)

Bu yetenek, işlev bağımsız değişkenlerinin ek tür denetimi gerektiğinde ve bir nesnenin sınıfına göre özel amaçlı kod yazmanız gerektiğinde en kullanışlıdır. Ancak, sanal işlevlerin işlevselliğini yinelediği için bu uygulama genellikle önerilmez.

Üye `CObject` işlev, `IsKindOf` belirli bir nesnenin belirli bir sınıfa ait olup olmadığını veya belirli bir sınıftan türetilip türetilmeyeceğini belirlemek için kullanılabilir. Bağımsız değişken, `IsKindOf` `CRuntimeClass` `RUNTIME_CLASS` sınıfın adı ile makro kullanarak alabilirsiniz bir nesnedir.

### <a name="to-use-the-runtime_class-macro"></a>RUNTIME_CLASS makroyu kullanmak için

1. Sınıf `RUNTIME_CLASS` `CObject`için burada gösterildiği gibi, sınıfın adı ile kullanın:

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

Çalışma zamanı sınıf nesnesine nadiren doğrudan erişmeniz gerekir. Daha yaygın bir kullanım, bir sonraki yordamda `IsKindOf` gösterildiği gibi çalışma zamanı sınıf nesnesini işleve geçirmektir. İşlev, `IsKindOf` belirli bir sınıfa ait olup olmadığını görmek için bir nesneyi sınar.

#### <a name="to-use-the-iskindof-function"></a>IsKindOf işlevini kullanmak için

1. Sınıfın çalışma zamanı sınıf desteğine sahip olduğundan emin olun. Diğer bir deyişle, sınıf doğrudan veya dolaylı `CObject` olarak türemiş `IMPLEMENT_DYNAMIC`olmalı `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE` **DECLARE** `DECLARE_SERIAL` _ `IMPLEMENT_SERIAL` **DYNAMIC** ve , ve , veya [cobject bir Sınıf Türetilmiş](../mfc/deriving-a-class-from-cobject.md)makalede açıklanan makrolar kullanılır .

1. Burada `IsKindOf` gösterildiği `CRuntimeClass` gibi, bağımsız değişkenoluşturmak için `RUNTIME_CLASS` makroyu kullanarak, o sınıfın nesneleri için üye işlevi çağırın:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  Nesne belirtilen sınıfın veya belirtilen sınıftan türetilen bir sınıfın **üyesiyse,** Doğru'yu döndürür. `IsKindOf`gerekirse türetilmiş Microsoft Foundation sınıflarınız için birden çok devralma veya sanal temel sınıfları desteklemez.

Çalışma zamanı sınıf bilgilerinin bir kullanımı nesnelerin dinamik oluşturulmasındadır. Bu [işlem, Dinamik Nesne Oluşturma](../mfc/dynamic-object-creation.md)makalesinde ele alınmıştır.

Serileştirme ve çalışma zamanı sınıf bilgileri hakkında daha ayrıntılı bilgi için MFC ve [Serialization'daki](../mfc/serialization-in-mfc.md) [dosyalar makalelerini](../mfc/files-in-mfc.md) görün.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Kullanma](../mfc/using-cobject.md)
