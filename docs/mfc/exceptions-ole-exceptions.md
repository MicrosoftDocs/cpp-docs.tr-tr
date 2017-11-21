---
title: "Özel durumlar: OLE özel durumları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE, exceptions
- OLE exceptions [MFC]
- exceptions [MFC], OLE
- exception handling [MFC], OLE
- OLE exceptions [MFC], classes for handling
ms.assetid: 2f8e0161-b94f-48bb-a5a2-6f644b192527
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4200f084ecfe441b0d17df0d71ebc03fcde081cb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-ole-exceptions"></a>Özel durumlar: OLE Özel Durumları
OLE özel durumları işlemek için tesis ve teknikleri diğer özel durumları işlemek için aynıdır. Özel durum işleme hakkında daha fazla bilgi için bkz: [C++ özel durum işleme](../cpp/cpp-exception-handling.md).  
  
 Soyut taban sınıfından türetilmiş tüm özel durum nesneleri `CException`. MFC OLE özel durumları işlemek için iki sınıfı sağlar:  
  
-   [COleException](../mfc/reference/coleexception-class.md) genel OLE özel durumları işlemek için.  
  
-   [COleDispatchException](../mfc/reference/coledispatchexception-class.md) (Otomasyonu) özel durumlar oluşturma ve OLE işleme gönderme için.  
  
 Sağlarlar ve kullanıldıkları bilgi miktarını iki bu sınıflar arasındaki farktır. `COleException`özel durum OLE durum kodunu içeren bir genel veri üyesi yok. `COleDispatchException`Aşağıdakiler de dahil olmak üzere daha fazla bilgi sağlar:  
  
-   Bir uygulamaya özgü hata kodu  
  
-   "Disk dolu" gibi bir hata açıklaması  
  
-   Uygulamanızın kullanıcı için ek bilgi sağlamak için kullanabileceğiniz bir Yardım bağlamı  
  
-   Uygulamanızın Yardım dosyasının adı  
  
-   Özel durum oluşturdu uygulamanın adı  
  
 `COleDispatchException`Daha fazla bilgi sunar, böylece ürünler gibi Microsoft Visual Basic ile birlikte kullanılabilir. Sözlü hata açıklaması, bir ileti kutusu veya diğer bildirim kullanılabilir; Yardım bilgileri, bir özel duruma neden olan koşulları yanıt kullanıcının yardımcı olmak için kullanılabilir.  
  
 İki genel işlevler karşılık gelen iki OLE özel durum sınıfları: [AfxThrowOleException](../mfc/reference/exception-processing.md#afxthrowoleexception) ve [AfxThrowOleDispatchException](../mfc/reference/exception-processing.md#afxthrowoledispatchexception). Genel OLE özel durumları ve OLE gönderme özel durumları, sırasıyla throw için bunları kullanın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Özel durum işleme](../mfc/exception-handling-in-mfc.md)

