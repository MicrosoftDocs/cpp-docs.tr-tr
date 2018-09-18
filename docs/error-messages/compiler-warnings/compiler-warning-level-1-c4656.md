---
title: Derleyici Uyarısı (düzey 1) C4656 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4656
dev_langs:
- C++
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3334b9448dd6e9d47ed0b3ee3e4dfb9dfc57b57f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46032422"
---
# <a name="compiler-warning-level-1-c4656"></a>Derleyici Uyarısı (düzey 1) C4656

'symbol': veri türü yeni veya en son yapımdan beri değiştirildi veya başka yerde farklı şekilde tanımlanmış

Eklediyseniz veya son başarılı yapıdan beri kaynak kodunuz için yeni yapmadan bir veri türü değiştirildi. Düzenle ve devam et, var olan veri türleri için değişiklikleri desteklemez.

Bu uyarı tarafından her zaman izlenir [önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumu sona erdirmeden bu uyarıyı kaldırmak için

1. Hata öncesinde durumuna geri dön veri türünü değiştirin.

1. Gelen **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Bu hata, kaynak kodunuzda değişiklik yapmadan kaldırmak için

1. Gelen **hata ayıklama** menüsünde seçin **hata ayıklamayı Durdur**.

1. Gelen **derleme** menüsünde seçin **yapı**.