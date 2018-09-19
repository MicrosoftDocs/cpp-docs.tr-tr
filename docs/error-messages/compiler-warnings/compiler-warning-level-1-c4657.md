---
title: Derleyici Uyarısı (düzey 1) C4657 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4657
dev_langs:
- C++
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0eb3701496b2300aa52f4734cb2d1ea6e236ad0a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098842"
---
# <a name="compiler-warning-level-1-c4657"></a>Derleyici Uyarısı (düzey 1) C4657

ifade en son yapımdan beri yeni olan bir veri türü gerektirir.

Eklediyseniz veya son başarılı yapıdan beri kaynak kodunuz için yeni yapmadan bir veri türü değiştirildi. Düzenle ve devam et, var olan veri türleri için değişiklikleri desteklemez.

Bu uyarı tarafından her zaman izlenir [önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumu sona erdirmeden bu uyarıyı kaldırmak için

1. Hata öncesinde durumuna geri dön veri türünü değiştirin.

1. Gelen **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Bu hata, kaynak kodunuzda değişiklik yapmadan kaldırmak için

1. Gelen **hata ayıklama** menüsünde seçin **hata ayıklamayı Durdur**.

1. Gelen **derleme** menüsünde seçin **yapı**.