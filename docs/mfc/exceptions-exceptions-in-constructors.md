---
title: 'Özel durumlar: Yapıcılardaki özel durumlar yönetme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [MFC], exceptions
- throwing exceptions [MFC], in constructors
- exceptions [MFC], in constructors
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3cab21255698c19046cfca185a0d8d7e7c530112
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421940"
---
# <a name="exceptions-exceptions-in-constructors"></a>Özel Durumlar: Yapıcılardaki Özel Durumlar

Bir oluşturucuda bir özel durum, hangi nesnelerin ve bellek ayırma özel durum atma önce açıklandığı gibi yaptığınız temiz [özel durumlar: özel durumları atma bilgisayarınızı kendi işlevlerden](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md).

Bir oluşturucuda bir özel durum, nesnenin kendisi için bellek Oluşturucu çağrılır zamanında zaten ayrıldı. Bu nedenle, derleyici otomatik olarak özel durum oluştuktan sonra nesnenin kapladığı bellek ayırması.

Daha fazla bilgi için [özel durumlar: özel durumlarda nesneleri serbest bırakma](../mfc/exceptions-freeing-objects-in-exceptions.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Özel Durum İşleme](../mfc/exception-handling-in-mfc.md)

