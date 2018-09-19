---
title: Önemli hata C1054 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 439019b1f510127ae54e77d445d59e86be09a49b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46101975"
---
# <a name="fatal-error-c1054"></a>Önemli hata C1054

Derleyici sınırı: başlatıcılar çok derin iç içe

Kod başlatıcıları (başlatılmakta türleri birleşiminin bağlı olarak 10-15 düzeyleri) iç içe geçme sınırı aşıyor.

### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümleri kullanarak düzeltmek için

1. İç içe geçme azaltmak için başlatılan veri türleri basitleştirin.

1. Ayrı deyim değişkenlerinde bildiriminden sonra başlatın.