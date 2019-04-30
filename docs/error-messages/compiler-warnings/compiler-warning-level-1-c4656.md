---
title: Derleyici Uyarısı (düzey 1) C4656
ms.date: 11/04/2016
f1_keywords:
- C4656
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
ms.openlocfilehash: 4285ce20f6131c2503304ed1bdb1bde02b2efcec
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375255"
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