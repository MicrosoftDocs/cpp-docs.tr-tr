---
title: İfade Değerlendirici Hatası CXX0015
ms.date: 11/04/2016
f1_keywords:
- CXX0015
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
ms.openlocfilehash: f73aef18563426d28a81b92b3c37d1b7e345d0d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662052"
---
# <a name="expression-evaluator-error-cxx0015"></a>İfade Değerlendirici Hatası CXX0015

ifade çok karmaşık (yığın taşması)

Girdiğiniz ifade çok karmaşık veya C ifade değerlendiricisi için kullanılabilir depolama alanı miktarı çok derin iç içe geçmiş.

Taşma genellikle çok fazla bekleyen hesaplamalar nedeniyle oluşur.

Hesaplanacak ifade diğer bölümleri için beklemek zorunda yerine ifade, karşılaştığından ifade'nın her bileşeninin değerlendirilebilir böylece bunları yeniden düzenleme.

İfade birden çok komutlarına bölün.

Bu hata için CAN0015 aynıdır.