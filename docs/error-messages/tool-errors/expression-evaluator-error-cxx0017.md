---
title: İfade Değerlendirici Hatası CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: 64ebce0161d67c298d55095f6bc409820120c34a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80196020"
---
# <a name="expression-evaluator-error-cxx0017"></a>İfade Değerlendirici Hatası CXX0017

sembol bulunamadı

İfadede belirtilen bir sembol bulunamadı.

Bu hatanın olası nedenlerinden biri, sembol adında bir büyük/küçük harf uyumsuzluğu olabilir. C ve C++ büyük/küçük harfe duyarlı diller olduğundan, kaynak üzerinde tanımlandığı tam durumda bir sembol adı verilmelidir.

Bu hata, hata ayıklama sırasında değişkeni izlemek için bir değişkeni oluşturmaya çalışırken ortaya çıkabilir. `typedef`, bir tür için yeni bir ad bildirir, ancak yeni bir tür tanımlamaz. Hata ayıklayıcıda denenen typecast, tanımlı bir tür adı gerektiriyor.

Bu hata CAN0017 ile aynıdır.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Simgenin kullanıldığı programdaki noktada zaten tanımlanmış olduğundan emin olun.

1. `typedef`tanımlı bir ad yerine, hata ayıklayıcıdaki değişkenleri dönüştürmek için gerçek tür adı kullanın.
