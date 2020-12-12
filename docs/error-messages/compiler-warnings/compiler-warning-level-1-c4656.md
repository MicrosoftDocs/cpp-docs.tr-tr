---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4656'
title: Derleyici Uyarısı (düzey 1) C4656
ms.date: 11/04/2016
f1_keywords:
- C4656
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
ms.openlocfilehash: d902a7f7629f8bcbadab4ead240c06ebbf1aa33c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318831"
---
# <a name="compiler-warning-level-1-c4656"></a>Derleyici Uyarısı (düzey 1) C4656

' symbol ': veri türü yeni veya son derlemeden bu yana değiştirilmiş ya da başka bir yerde farklı tanımlanmış

Son başarılı derlemeden bu yana kaynak kodunuzla yeni hale getirerek bir veri türü eklediniz veya değiştirdiniz. Düzenle ve devam et, varolan veri türlerinde yapılan değişiklikleri desteklemez.

Bu uyarı, her zaman [önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)tarafından izlenir. Daha fazla bilgi için [desteklenen kod değişikliklerine](/visualstudio/debugger/supported-code-changes-cpp)bakın.

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumunu sonlandırmadan bu uyarıyı kaldırmak için

1. Veri türünü hatadan önceki durumuna geri çevirin.

1. **Hata Ayıkla** menüsünde, **kod değişikliklerini Uygula**' yı seçin.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Kaynak kodunuzu değiştirmeden bu hatayı kaldırmak için

1. **Hata Ayıkla** menüsünden **hata ayıklamayı Durdur**' u seçin.

1. **Yapı** menüsünden **Oluştur**' u seçin.
