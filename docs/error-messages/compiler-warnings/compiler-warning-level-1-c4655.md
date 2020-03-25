---
title: Derleyici Uyarısı (düzey 1) C4655
ms.date: 08/27/2018
f1_keywords:
- C4655
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
ms.openlocfilehash: d4c409c2d69099853a872142e05ef0fcda5a7655
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199537"
---
# <a name="compiler-warning-level-1-c4655"></a>Derleyici Uyarısı (düzey 1) C4655

> '*symbol*': değişken türü son derlemeden beri yeni veya başka yerde farklı tanımlanmış

## <a name="remarks"></a>Açıklamalar

Son başarılı derlemeden bu yana yeni bir veri türü değiştirdiniz veya eklediniz. Düzenle ve devam et, varolan veri türlerinde yapılan değişiklikleri desteklemez.

Bu uyarının ardından [önemli bir hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Daha fazla bilgi için [desteklenen kod değişikliklerine](/visualstudio/debugger/supported-code-changes-cpp)bakın.

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumunu sonlandırmadan bu uyarıyı kaldırmak için

1. Veri türünü hatadan önceki durumuna geri çevirin.

2. **Hata Ayıkla** menüsünde, **kod değişikliklerini Uygula**' yı seçin.

### <a name="to-remove-this-warning-without-changing-your-source-code"></a>Kaynak kodunuzu değiştirmeden bu uyarıyı kaldırmak için

1. **Hata Ayıkla** menüsünden **hata ayıklamayı Durdur**' u seçin.

2. **Yapı** menüsünden **Oluştur**' u seçin.
