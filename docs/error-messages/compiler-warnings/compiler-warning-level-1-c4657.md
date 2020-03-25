---
title: Derleyici Uyarısı (düzey 1) C4657
ms.date: 11/04/2016
f1_keywords:
- C4657
helpviewer_keywords:
- C4657
ms.assetid: eb750050-cea6-4ead-b80c-d5dcd4971cfc
ms.openlocfilehash: 6cc049d99339a6f19ca86cd5c7a10f062a1451a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199507"
---
# <a name="compiler-warning-level-1-c4657"></a>Derleyici Uyarısı (düzey 1) C4657

ifade, son derlemeden beri yeni olan bir veri türü içeriyor

Son başarılı derlemeden bu yana kaynak kodunuzla yeni hale getirerek bir veri türü eklediniz veya değiştirdiniz. Düzenle ve devam et, varolan veri türlerinde yapılan değişiklikleri desteklemez.

Bu uyarı, her zaman [önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md)tarafından izlenir. Daha fazla bilgi için [desteklenen kod değişikliklerine](/visualstudio/debugger/supported-code-changes-cpp)bakın.

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumunu sonlandırmadan bu uyarıyı kaldırmak için

1. Veri türünü hatadan önceki durumuna geri çevirin.

1. **Hata Ayıkla** menüsünde, **kod değişikliklerini Uygula**' yı seçin.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Kaynak kodunuzu değiştirmeden bu hatayı kaldırmak için

1. **Hata Ayıkla** menüsünden **hata ayıklamayı Durdur**' u seçin.

1. **Yapı** menüsünden **Oluştur**' u seçin.
