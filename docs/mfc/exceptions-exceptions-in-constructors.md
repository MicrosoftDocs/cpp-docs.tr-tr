---
description: 'Daha fazla bilgi edinin: özel durumlar: Oluşturuculardaki özel durumlar'
title: 'Özel Durumlar: Yapıcılardaki Özel Durumlar'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 69393cc6a5cf709d359ccbdb572406e91c6788ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290602"
---
# <a name="exceptions-exceptions-in-constructors"></a>Özel Durumlar: Yapıcılardaki Özel Durumlar

Bir oluşturucuda özel durum oluştururken özel [durumlar: kendi Işlevlerinizden özel durumlar](exceptions-throwing-exceptions-from-your-own-functions.md)oluşturma bölümünde açıklandığı gibi özel durumu oluşturmadan önce yaptığınız nesne ve bellek ayırmalarını temizleyin.

Bir oluşturucuda özel durum oluştururken nesnenin kendisi için bellek, oluşturucunun çağrıldığı zamana göre zaten ayrılır. Bu nedenle, derleyici özel durum oluşturulduktan sonra nesnenin kapladığı belleği otomatik olarak serbest bırakılır.

Daha fazla bilgi için bkz. [özel durumlar: nesneleri özel durumlarla boşaltma](exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](exception-handling-in-mfc.md)
