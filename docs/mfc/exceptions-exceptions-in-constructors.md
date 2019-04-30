---
title: 'Özel durumlar: Yapıcılardaki özel durumlar'
ms.date: 11/04/2016
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
ms.openlocfilehash: 0b11f5be18879d5ad4b9e204bb02e18b4617c6b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405878"
---
# <a name="exceptions-exceptions-in-constructors"></a>Özel durumlar: Yapıcılardaki özel durumlar

Bir oluşturucuda bir özel durum, hangi nesnelerin ve bellek ayırma özel durum atma önce açıklandığı gibi yaptığınız temiz [özel durumlar: Kendi İşlevlerinizden özel durumları atma](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

Bir oluşturucuda bir özel durum, nesnenin kendisi için bellek Oluşturucu çağrılır zamanında zaten ayrıldı. Bu nedenle, derleyici otomatik olarak özel durum oluştuktan sonra nesnenin kapladığı bellek ayırması.

Daha fazla bilgi için [özel durumlar: Özel durumlarda nesneleri serbest bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)
