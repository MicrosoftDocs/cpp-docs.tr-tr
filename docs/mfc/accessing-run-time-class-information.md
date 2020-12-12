---
description: 'Hakkında daha fazla bilgi edinin: Run-Time sınıf bilgilerine erişme'
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
ms.openlocfilehash: fb5877a3ac6ece58ed46bde2b5fbdcc49db10351
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169482"
---
# <a name="accessing-run-time-class-information"></a>Çalışma Süresi Sınıf Bilgilerine Erişme

Bu makalede, çalışma zamanında bir nesnenin sınıfıyla ilgili bilgilere nasıl erişebileceğiniz açıklanır.

> [!NOTE]
> MFC Visual C++ 4,0 ' de tanıtılan [çalışma zamanı tür bilgisi](../cpp/run-time-type-information.md) (RTTI) desteğini kullanmaz.

Bir sınıfı [CObject](reference/cobject-class.md) 'ten türemiş **ve,** ,  `IMPLEMENT_DYNAMIC` `DECLARE_DYNCREATE` ve, ve, ve ' yi, ve `IMPLEMENT_DYNCREATE` ' ı `DECLARE_SERIAL` `IMPLEMENT_SERIAL` [bir sınıf türeten bir sınıf türet](deriving-a-class-from-cobject.md) `CObject` .

Bu özellik, işlev bağımsız değişkenlerinin ek tür denetlemesi gerektiğinde ve bir nesnenin sınıfına göre özel amaçlı kod yazmanız gerektiğinde faydalıdır. Ancak, bu uygulama genellikle önerilmez çünkü sanal işlevlerin işlevlerini yinelemeyor.

`CObject`Üye işlevi, `IsKindOf` belirli bir nesnenin belirtilen sınıfa ait olup olmadığını veya belirli bir sınıftan türetilmediğini anlamak için kullanılabilir. İçin bağımsız değişkeni `IsKindOf` `CRuntimeClass` , `RUNTIME_CLASS` makroyu sınıfının adıyla birlikte kullanmaya alabileceğiniz bir nesnedir.

### <a name="to-use-the-runtime_class-macro"></a>RUNTIME_CLASS makrosunu kullanmak için

1. Sınıfı `RUNTIME_CLASS` için burada gösterildiği gibi, sınıfının adıyla kullanın `CObject` :

   [!code-cpp[NVC_MFCCObjectSample#4](codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

Genellikle çalışma zamanı sınıf nesnesine doğrudan erişmeniz gerekecektir. Daha yaygın bir kullanım, bir `IsKindOf` sonraki yordamda gösterildiği gibi çalışma zamanı sınıf nesnesini işleve iletmektir. `IsKindOf`İşlevi, belirli bir sınıfa ait olup olmadığını görmek için bir nesnesi sınar.

#### <a name="to-use-the-iskindof-function"></a>IsKindOf işlevini kullanmak için

1. Sınıfın çalışma zamanı sınıf desteğine sahip olduğundan emin olun. Diğer bir deyişle, sınıfın doğrudan veya dolaylı olarak öğesinden türetilmiş olması gerekir `CObject` ve **Bu,,** `IMPLEMENT_DYNAMIC` `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE` , ya da `DECLARE_SERIAL` `IMPLEMENT_SERIAL` [CObject 'ten bir sınıf türetiliyor](deriving-a-class-from-cobject.md)makalesinde açıklanan, ve, ya da ve makroları kullanır.

1. `IsKindOf` `RUNTIME_CLASS` `CRuntimeClass` Burada gösterildiği gibi, bağımsız değişkenini oluşturmak için makroyu kullanarak bu sınıfın nesneleri için üye işlevini çağırın:

   [!code-cpp[NVC_MFCCObjectSample#2](codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  Nesne belirtilen sınıfın veya belirtilen sınıftan türetilmiş bir sınıfın üyesiyse IsKindOf **true** değerini döndürür. `IsKindOf` , birden fazla devralmayı veya sanal temel sınıfı desteklemez, ancak gerekirse, türetilmiş Microsoft Foundation sınıflarınız için birden fazla devralma de kullanabilirsiniz.

Çalışma zamanı sınıf bilgilerinin bir kullanımı, nesnelerin dinamik olarak oluşturulmasına sahiptir. Bu işlem, [dinamik nesne oluşturma](dynamic-object-creation.md)makalesinde ele alınmıştır.

Serileştirme ve çalışma zamanı sınıfı bilgileri hakkında daha ayrıntılı bilgi için bkz. MFC ve serileştirme [içindeki makaleler dosyaları](files-in-mfc.md) . [](serialization-in-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[CObject Kullanma](using-cobject.md)
