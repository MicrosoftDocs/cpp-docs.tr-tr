---
title: Önemli hata C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: af43ddb83e872762f720b156644e0d466957a8a7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80203885"
---
# <a name="fatal-error-c1092"></a>Önemli hata C1092

Düzenle ve devam et veri türlerinde yapılan değişiklikleri desteklemez; derleme gerekiyor

Son başarılı derlemeden bu yana bir veri türü değiştirdiniz veya eklediniz.

- Düzenle ve devam et, sınıf, yapı veya Enum tanımları dahil olmak üzere mevcut veri türlerinde yapılan değişiklikleri desteklemez. Hata ayıklamayı durdurmanız ve uygulamayı derlemeniz gerekir.

- VC*x*0. pdb ( *x* , kullanılan görselin C++ ana sürümü) salt okunurdur gibi bir program veritabanı dosyası ise Düzenle ve devam et yeni veri türlerinin eklenmesini desteklemez. Veri türleri eklemek için derleyicinin. pdb dosyasını yazma modunda açması gerekir.

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumunu sonlandırmadan bu hatayı kaldırmak için

1. Veri türünü hatadan önceki durumuna geri çevirin.

1. **Hata Ayıkla** menüsünde, **kod değişikliklerini Uygula**' yı seçin.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Kaynak kodunuzu değiştirmeden bu hatayı kaldırmak için

1. **Hata Ayıkla** menüsünden **hata ayıklamayı Durdur**' u seçin.

1. **Yapı** menüsünden **Oluştur**' u seçin.

Daha fazla bilgi için [desteklenen kod değişikliklerine](/visualstudio/debugger/supported-code-changes-cpp)bakın.
