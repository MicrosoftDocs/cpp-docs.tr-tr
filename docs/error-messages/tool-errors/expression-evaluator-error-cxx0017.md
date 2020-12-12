---
description: 'Daha fazla bilgi edinin: Ifade değerlendirici hatası CXX0017'
title: İfade Değerlendirici Hatası CXX0017
ms.date: 11/04/2016
f1_keywords:
- CXX0017
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
ms.openlocfilehash: 0abb99422383f95e13d4137a5ad899730d485f87
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228280"
---
# <a name="expression-evaluator-error-cxx0017"></a>İfade Değerlendirici Hatası CXX0017

sembol bulunamadı

İfadede belirtilen bir sembol bulunamadı.

Bu hatanın olası nedenlerinden biri, sembol adında bir büyük/küçük harf uyumsuzluğu olabilir. C ve C++ büyük/küçük harfe duyarlı diller olduğundan, kaynak üzerinde tanımlandığı tam durumda bir sembol adı verilmelidir.

Bu hata, hata ayıklama sırasında değişkeni izlemek için bir değişkeni oluşturmaya çalışırken ortaya çıkabilir. , `typedef` Bir tür için yeni bir ad bildirir, ancak yeni bir tür tanımlamaz. Hata ayıklayıcıda denenen typecast, tanımlı bir tür adı gerektiriyor.

Bu hata CAN0017 ile aynıdır.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltilmesi için

1. Simgenin kullanıldığı programdaki noktada zaten tanımlanmış olduğundan emin olun.

1. Hata ayıklayıcı içinde, tanımlı bir ad yerine değişkenleri dönüştürmek için gerçek tür adı kullanın `typedef` .
