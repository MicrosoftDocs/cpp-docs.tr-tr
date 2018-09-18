---
title: İfade değerlendirici hatası CXX0015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0015
dev_langs:
- C++
helpviewer_keywords:
- CXX0015
- CAN0015
ms.assetid: 35efaf77-d578-48d8-bfc5-fdeb2a46a8b5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1aa37a2cc7208063ce4cfa786de196842ab42b45
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050822"
---
# <a name="expression-evaluator-error-cxx0015"></a>İfade Değerlendirici Hatası CXX0015

ifade çok karmaşık (yığın taşması)

Girdiğiniz ifade çok karmaşık veya C ifade değerlendiricisi için kullanılabilir depolama alanı miktarı çok derin iç içe geçmiş.

Taşma genellikle çok fazla bekleyen hesaplamalar nedeniyle oluşur.

Hesaplanacak ifade diğer bölümleri için beklemek zorunda yerine ifade, karşılaştığından ifade'nın her bileşeninin değerlendirilebilir böylece bunları yeniden düzenleme.

İfade birden çok komutlarına bölün.

Bu hata için CAN0015 aynıdır.