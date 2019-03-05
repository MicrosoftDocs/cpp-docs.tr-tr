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
ms.openlocfilehash: 2e4f8685033fc7a8a2f49dafa7ef4e4e019d8989
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298834"
---
# <a name="accessing-run-time-class-information"></a>Çalışma Süresi Sınıf Bilgilerine Erişme

Bu makalede, çalışma zamanında bir nesnenin sınıfını hakkında bilgilere erişmek açıklanmaktadır.

> [!NOTE]
>  MFC kullanmayan [çalışma zamanı türü bilgileri](../cpp/run-time-type-information.md) Visual C++ 4.0 sunulan (RTTI) desteği.

Varsa, sınıfından türetilmiş [CObject](../mfc/reference/cobject-class.md) ve kullanılan **DECLARE**_**dinamik** ve `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE`, veya `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları makalesinde açıklanan [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md), `CObject` sınıfında özelliği çalışma zamanında tam bir nesnenin sınıfını belirler.

Bu özellik, ek türü işlev bağımsız değişkenleri denetimini gerektiğinde ve bir nesne sınıfına göre özel amaçlı kod yazmanız gerekir en yararlı olur. Ancak, sanal işlevler işlevselliğini yineleyen çünkü bu yöntem genellikle önerilmez.

`CObject` Üye işlevi `IsKindOf` belirli bir nesne için belirli bir sınıf dahilse veya belirli bir sınıftan türetilmişse belirlemek için kullanılabilir. Bağımsız değişkeni `IsKindOf` olduğu bir `CRuntimeClass` kullanarak elde nesnesi `RUNTIME_CLASS` sınıfın adı ile makrosu.

### <a name="to-use-the-runtimeclass-macro"></a>RUNTIME_CLASS makrosunu kullanmak için

1. Kullanım `RUNTIME_CLASS` sınıf için burada gösterildiği gibi sınıfın adıyla `CObject`:

   [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/cpp/accessing-run-time-class-information_1.cpp)]

Nadiren, çalışma zamanı sınıf nesneye doğrudan erişim gerekir. Daha yaygın bir kullanım için çalışma zamanı sınıf nesnesi geçirmektir `IsKindOf` sonraki yordamda gösterildiği gibi işlev. `IsKindOf` İşlevi, bir nesne belirli bir sınıfa ait olup olmadığını görmek için sınar.

#### <a name="to-use-the-iskindof-function"></a>Iskindof işlevi kullanmak için

1. Çalışma zamanı sınıf destek sınıfı olduğundan emin olun. Diğer bir deyişle, sınıfı doğrudan veya dolaylı olarak elde gerekir `CObject` ve kullanılan **DECLARE**_**dinamik** ve `IMPLEMENT_DYNAMIC`, `DECLARE_DYNCREATE` ve `IMPLEMENT_DYNCREATE`, veya `DECLARE_SERIAL` ve `IMPLEMENT_SERIAL` makroları makalesinde açıklanan [CObject'ten sınıf türetme](../mfc/deriving-a-class-from-cobject.md).

1. Çağrı `IsKindOf` üye işlevi için bu sınıfın nesneleri kullanarak `RUNTIME_CLASS` oluşturulacak makrosu `CRuntimeClass` bağımsız değişkeni, burada gösterildiği gibi:

   [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/cpp/accessing-run-time-class-information_2.h)]

   [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/cpp/accessing-run-time-class-information_3.cpp)]

    > [!NOTE]
    >  Iskindof döndürür **TRUE** nesnenin belirtilen sınıfın veya belirtilen sınıftan türetilmiş bir sınıfın üye ise. `IsKindOf` Gerekirse, türetilmiş Microsoft Foundation sınıfları için birden çok devralma kullanabilirsiniz, ancak birden çok devralma veya sanal temel sınıflar desteklemez.

Bir çalışma süresi sınıf bilgilerine nesnelerin dinamik oluşturmada kullanılır. Bu işlem makalesinde açıklanan [dinamik Nesne oluşturma](../mfc/dynamic-object-creation.md).

Daha ayrıntılı çalışma zamanı sınıf bilgileri ve seri hale getirme hakkında bilgi için makalelerine bakın [MFC'deki dosyalar](../mfc/files-in-mfc.md) ve [serileştirme](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Ayrıca bkz.

[CObject Kullanma](../mfc/using-cobject.md)
