---
title: İfade Değerlendirici Hatası CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: bbf16ae9a503a8525edb42d6bf1fc4336c3f5267
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602544"
---
# <a name="expression-evaluator-error-cxx0017"></a>İfade Değerlendirici Hatası CXX0017

Sembol bulunamadı

Belirtilen bir ifadede bir sembolü bulunamadı.

Bu hatanın olası nedenlerinden biri, sembol adı büyük/küçük harf uyuşmazlık olmasıdır. C ve C++ dilleri büyük küçük harfe duyarlı olduğundan, kaynak olarak tanımlandığı tam durumda bir sembol adı verilmesi gerekir.

Bu hata, hata ayıklama sırasında değişkeni izlemek için bir değişken türü atayarak çalışırken ortaya çıkabilir. `typedef` Bir türü için yeni bir ad bildirir ancak yeni bir tür tanımlamıyor. Hata ayıklayıcıda çalıştı typecast tanımlanan bir tür adı gerektirir.

Bu hata için CAN0017 aynıdır.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. Sembol zaten kullanıldığı yerin programda bir noktada bildirildiğinden emin olun.

1. Gerçek tür adı hata ayıklayıcıda değişkenler olarak kullanmak yerine `typedef`-tanımlanan adı.