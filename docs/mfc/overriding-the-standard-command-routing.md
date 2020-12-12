---
description: 'Hakkında daha fazla bilgi edinin: standart komut yönlendirmeyi geçersiz kılma'
title: Standart Komut Yönlendirmeyi Geçersiz Kılma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, command routing
- command routing [MFC], overriding
- command handling [MFC], routing commands
- overriding, standard command routing
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
ms.openlocfilehash: 5241e767beee85f92875128cc5ebccd1a23477f5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205999"
---
# <a name="overriding-the-standard-command-routing"></a>Standart Komut Yönlendirmeyi Geçersiz Kılma

Nadir durumlarda, standart Framework yönlendirmenin bazı çeşitlerinizi uygulamanız gerektiğinde geçersiz kılabilirsiniz. Fikir, bu sınıfların üzerine yazarak bir veya daha fazla sınıftaki yönlendirmeyi değiştirmenizde yarar vardır `OnCmdMsg` . Bunu yapın:

- Sınıf içinde, varsayılan olmayan bir nesneye geçirilecek sırayı keser.

- Yeni varsayılan olmayan nesnede veya komut hedeflerinde, komutları öğesine geçirebilir.

Yönlendirmeye yeni bir nesne eklerseniz, sınıfının sınıfı bir komut hedef sınıfı olmalıdır. Geçersiz kılma sürümleriniz içinde `OnCmdMsg` , geçersiz kıldığınızı sürümü çağırdığınızdan emin olun. MFC başvurusu içindeki sınıfın [OnCmdMsg](reference/ccmdtarget-class.md#oncmdmsg) üye işlevine `CCmdTarget` ve bu  sınıfların içindeki sürümlere `CView` ve `CDocument` örnekler için sağlanan kaynak koda bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve bir Işleyiciyi nasıl çağırır](how-the-framework-calls-a-handler.md)
