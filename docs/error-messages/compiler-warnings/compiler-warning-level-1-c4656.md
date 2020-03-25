---
title: Derleyici Uyarısı (düzey 1) C4656
ms.date: 11/04/2016
f1_keywords:
- C4656
helpviewer_keywords:
- C4656
ms.assetid: b5aaef74-2320-4345-a6ae-b813881a491c
ms.openlocfilehash: a78da51a99aa924eadbf5c9f458ceb0a75889141
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80175655"
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
