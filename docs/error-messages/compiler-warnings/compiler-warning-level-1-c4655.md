---
title: Derleyici Uyarısı (düzey 1) C4655
ms.date: 08/27/2018
f1_keywords:
- C4655
helpviewer_keywords:
- C4655
ms.assetid: 540f2c7a-e4a1-49af-84b4-03eeea1bbf41
ms.openlocfilehash: aff78dbed217a6d9c5bc2a315ef12a33fe6caf0d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62374670"
---
# <a name="compiler-warning-level-1-c4655"></a>Derleyici Uyarısı (düzey 1) C4655

> '*sembol*': değişken türü son yapımdan beri yeni veya başka yerde farklı şekilde tanımlanmış

## <a name="remarks"></a>Açıklamalar

Değiştirdiğiniz ya da başarılı en son yapımdan beri yeni bir veri türüne eklendi. Düzenle ve devam et, var olan veri türleri için değişiklikleri desteklemez.

Bu uyarı tarafından izlenen bir [önemli hata C1092](../../error-messages/compiler-errors-1/fatal-error-c1092.md). Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri](/visualstudio/debugger/supported-code-changes-cpp).

### <a name="to-remove-this-warning-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumu sona erdirmeden bu uyarıyı kaldırmak için

1. Hata öncesinde durumuna geri dön veri türünü değiştirin.

2. Gelen **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.

### <a name="to-remove-this-warning-without-changing-your-source-code"></a>Kaynak kodunuzu değiştirmeden bu uyarıyı kaldırmak için

1. Gelen **hata ayıklama** menüsünde seçin **hata ayıklamayı Durdur**.

2. Gelen **derleme** menüsünde seçin **yapı**.