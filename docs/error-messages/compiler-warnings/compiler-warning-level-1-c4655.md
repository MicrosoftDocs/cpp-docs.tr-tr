---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4655'
title: Derleyici Uyarısı (düzey 1) C4655
ms.date: 08/27/2018
f1_keywords:
- C4655
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
ms.openlocfilehash: 2573ac5410114a0fe4ff4b074b83bbbb2efc8c97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318798"
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
