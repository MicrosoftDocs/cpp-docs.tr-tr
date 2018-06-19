---
title: 'Özel durumlar: OLE özel durumları | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 991848e9b5b78ad960fb8ed0bdf09dd56db47e2c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33345547"
---
# <a name="exceptions-ole-exceptions"></a>Özel durumlar: OLE Özel Durumları
OLE özel durumları işlemek için tesis ve teknikleri diğer özel durumları işlemek için aynıdır. Özel durum işleme hakkında daha fazla bilgi için bkz: [C++ özel durum işleme](../cpp/cpp-exception-handling.md).  
  
 Soyut taban sınıfından türetilmiş tüm özel durum nesneleri `CException`. MFC OLE özel durumları işlemek için iki sınıfı sağlar:  
  
-   [COleException](../mfc/reference/coleexception-class.md) genel OLE özel durumları işlemek için.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) (Otomasyonu) özel durumlar oluşturma ve OLE işleme gönderme için.  
  
 Sağlarlar ve kullanıldıkları bilgi miktarını iki bu sınıflar arasındaki farktır. `COleException` özel durum OLE durum kodunu içeren bir genel veri üyesi yok. `COleDispatchException` Aşağıdakiler de dahil olmak üzere daha fazla bilgi sağlar:  
  
-   Bir uygulamaya özgü hata kodu  
  
-   "Disk dolu" gibi bir hata açıklaması  
  
-   Uygulamanızın kullanıcı için ek bilgi sağlamak için kullanabileceğiniz bir Yardım bağlamı  
  
-   Uygulamanızın Yardım dosyasının adı  
  
-   Özel durum oluşturdu uygulamanın adı  
  
 `COleDispatchException` Daha fazla bilgi sunar, böylece ürünler gibi Microsoft Visual Basic ile birlikte kullanılabilir. Sözlü hata açıklaması, bir ileti kutusu veya diğer bildirim kullanılabilir; Yardım bilgileri, bir özel duruma neden olan koşulları yanıt kullanıcının yardımcı olmak için kullanılabilir.  
  
 İki genel işlevler karşılık gelen iki OLE özel durum sınıfları: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) ve [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Genel OLE özel durumları ve OLE gönderme özel durumları, sırasıyla throw için bunları kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

