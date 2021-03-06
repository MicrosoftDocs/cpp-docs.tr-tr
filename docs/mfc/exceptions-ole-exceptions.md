---
description: 'Daha fazla bilgi edinin: özel durumlar: OLE özel durumları'
title: 'Özel durumlar: OLE Özel Durumları'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
ms.openlocfilehash: da2a92d23dc7c11735c75482febea60916af289f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290524"
---
# <a name="exceptions-ole-exceptions"></a>Özel durumlar: OLE Özel Durumları

OLE 'de özel durumları işlemeye yönelik teknikler ve tesisler, diğer özel durumları işlemeye yönelik olanlarla aynıdır. Özel durum işleme hakkında daha fazla bilgi için, [özel durumlar ve hata işleme Için modern C++ en iyi uygulamaları](../cpp/errors-and-exception-handling-modern-cpp.md)makalesine bakın.

Tüm özel durum nesneleri soyut temel sınıftan türetilir `CException` . MFC OLE özel durumlarını işlemek için iki sınıf sağlar:

- [Colet özel durumu](reference/coleexception-class.md) Genel OLE özel durumlarını işlemek için.

- [Cotadispatchexception](reference/coledispatchexception-class.md) OLE dağıtım (Otomasyon) özel durumları oluşturmak ve işlemek için.

Bu iki sınıf arasındaki fark, sağladıkları ve nerede kullanıldıkları bilgi miktarıdır. `COleException` özel durum için OLE durum kodunu içeren bir genel veri üyesine sahiptir. `COleDispatchException` Aşağıdakiler de dahil olmak üzere daha fazla bilgi sağlar:

- Uygulamaya özgü hata kodu

- "Disk dolu" gibi bir hata açıklaması

- Uygulamanızın Kullanıcı için ek bilgi sağlamak üzere kullanabileceği bir yardım bağlamı

- Uygulamanızın Yardım dosyasının adı

- Özel durumu oluşturan uygulamanın adı

`COleDispatchException` Microsoft Visual Basic gibi ürünlerle kullanılabilmesi için daha fazla bilgi sağlar. Sözlü hatası açıklaması bir ileti kutusu veya başka bir bildirimde kullanılabilir; Yardım bilgileri, kullanıcının özel duruma neden olan koşullara yanıt vermesini sağlamak için kullanılabilir.

İki genel işlev iki OLE özel durum sınıfına karşılık gelir: [AfxThrowOleException](reference/exception-processing.md#afxthrowoleexception) ve [AfxThrowOleDispatchException](reference/exception-processing.md#afxthrowoledispatchexception). Bunları, sırasıyla Genel OLE özel durumları ve OLE dağıtım özel durumları oluşturmak için kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
