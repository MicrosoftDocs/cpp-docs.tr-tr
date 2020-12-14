---
description: 'Hakkında daha fazla bilgi edinin: nesneleri One-Stage ve Two-Stage oluşturma'
title: Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı
ms.date: 11/04/2016
helpviewer_keywords:
- objects [MFC], creating graphic objects
- object creation [MFC], graphic objects
- objects [MFC], graphic objects
- one-stage and two-stage construction of objects [MFC]
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
ms.openlocfilehash: d46a8d380c263c4ce18671f02b11d5b058bc8410
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243919"
---
# <a name="one-stage-and-two-stage-construction-of-objects"></a>Nesnelerin Tek Aşamalı ve İki Aşamalı Yapımı

Kalem ve fırçalar gibi grafik nesneleri oluşturmak için iki teknik arasında seçim yapabilirsiniz:

- *Tek aşamalı oluşturma*: tüm Oluşturucu ile nesneyi tek bir aşamada oluşturun ve başlatın.

- *İki aşamalı oluşturma*: nesneyi iki ayrı aşamada oluşturun ve başlatın. Oluşturucu nesnesini oluşturur ve bir başlatma işlevi başlatır.

İki aşamalı oluşturma her zaman güvenlidir. Tek aşamalı bir yapım sırasında, yanlış bağımsız değişkenler sağlarsanız veya bellek ayırma başarısız olursa Oluşturucu bir özel durum oluşturabilir. Bu sorunun iki aşamalı oluşturma nedeniyle kaçınılması, ancak hata olup olmadığını kontrol etmeniz gerekir. Her iki durumda da, nesneyi yok etmek aynı işlemdir.

> [!NOTE]
> Bu teknikler yalnızca grafik nesneleri değil herhangi bir nesne oluşturmak için geçerlidir.

## <a name="example-of-both-construction-techniques"></a>Her Iki oluşturma tekniği örneği

Aşağıdaki kısa örnek, bir kalem nesnesi oluşturma yöntemlerinin her ikisini de göstermektedir:

[!code-cpp[NVC_MFCDocViewSDI#6](codesnippet/cpp/one-stage-and-two-stage-construction-of-objects_1.cpp)]

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Grafik nesneler](graphic-objects.md)

- [Bir cihaz bağlamına grafik nesnesi seçme](selecting-a-graphic-object-into-a-device-context.md)

- [Cihaz bağlamları](device-contexts.md)

- [Bir görünümde çizim yapma](drawing-in-a-view.md)

## <a name="see-also"></a>Ayrıca bkz.

[Grafik nesneleri](graphic-objects.md)
