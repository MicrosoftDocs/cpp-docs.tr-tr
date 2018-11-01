---
title: 'Özel durumlar: OLE Özel Durumları'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
ms.openlocfilehash: 2732f571d305fda2b739be02661ab9558f8bc653
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515430"
---
# <a name="exceptions-ole-exceptions"></a>Özel durumlar: OLE Özel Durumları

Teknikleri ve özellikleri OLE özel durumları işleme için bu diğer özel durumları işlemek için aynıdır. Özel durum işleme hakkında daha fazla bilgi için bkz [C++ özel durum işleme](../cpp/cpp-exception-handling.md).

Tüm özel durum nesneleri soyut taban sınıfından türetilen `CException`. MFC, OLE özel durumları işlemek için iki sınıf sağlar:

- [COleException](../mfc/reference/coleexception-class.md) genel OLE özel durumları işlemek için.

- [COleDispatchException](../mfc/reference/coledispatchexception-class.md) (Otomasyon) özel durumlar oluşturma ve işleme OLE gönderme için.

Bu iki sınıf arasındaki farktır kullanıldıkları ve sağladıkları bilgi miktarı. `COleException` özel durum için OLE durum kodu içeren genel veri üyesine sahip. `COleDispatchException` Aşağıdakiler dahil olmak üzere daha fazla bilgi sağlar:

- Bir uygulamaya özgü hata kodu

- "Disk dolu" gibi bir hata açıklaması

- Uygulamanızın kullanıcı için ek bilgi sağlamak için kullanabileceğiniz bir Yardım içeriği

- Uygulamanızın Yardım dosyasının adı

- Özel durumu oluşturan uygulamanın adı

`COleDispatchException` Daha fazla bilgi sağlar, böylece ürünler gibi Microsoft Visual Basic ile kullanılabilir. Sözlü hata açıklamasını, bir ileti kutusu veya diğer bildirim kullanılabilir; Yardım bilgileri, özel duruma neden olan koşulları için yanıt kullanıcının yardımcı olmak için kullanılabilir.

İki genel işlevleri, iki OLE özel durum sınıfları karşılık gelir: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) ve [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Genel OLE özel durumları ve OLE gönderme özel durumları, sırasıyla throw için bunları kullanın.

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

