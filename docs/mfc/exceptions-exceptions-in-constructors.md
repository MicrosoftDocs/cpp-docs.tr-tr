---
title: 'Özel Durumlar: Yapıcılardaki Özel Durumlar'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 4089f4d44f03c7de3432f137b5d28f74189e1cb9
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624612"
---
# <a name="exceptions-exceptions-in-constructors"></a>Özel Durumlar: Yapıcılardaki Özel Durumlar

Bir oluşturucuda özel durum oluştururken özel [durumlar: kendi Işlevlerinizden özel durumlar](exceptions-throwing-exceptions-from-your-own-functions.md)oluşturma bölümünde açıklandığı gibi özel durumu oluşturmadan önce yaptığınız nesne ve bellek ayırmalarını temizleyin.

Bir oluşturucuda özel durum oluştururken nesnenin kendisi için bellek, oluşturucunun çağrıldığı zamana göre zaten ayrılır. Bu nedenle, derleyici özel durum oluşturulduktan sonra nesnenin kapladığı belleği otomatik olarak serbest bırakılır.

Daha fazla bilgi için bkz. [özel durumlar: nesneleri özel durumlarla boşaltma](exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
