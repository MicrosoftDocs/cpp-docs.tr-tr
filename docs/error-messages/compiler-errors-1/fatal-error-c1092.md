---
description: 'Daha fazla bilgi edinin: önemli hata C1092'
title: Önemli hata C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: b2a16991784b901202e5d51c0d256ad48305f55f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145138"
---
# <a name="fatal-error-c1092"></a>Önemli hata C1092

Düzenle ve devam et veri türlerinde yapılan değişiklikleri desteklemez; derleme gerekiyor

Son başarılı derlemeden bu yana bir veri türü değiştirdiniz veya eklediniz.

- Düzenle ve devam et, sınıf, yapı veya Enum tanımları dahil olmak üzere mevcut veri türlerinde yapılan değişiklikleri desteklemez. Hata ayıklamayı durdurmanız ve uygulamayı derlemeniz gerekir.

- VC *x* 0. pdb ( *x* kullanılan Visual C++ ana sürümüdür) gibi bir program veritabanı dosyası salt okunurdur, Düzenle ve devam et, yeni veri türlerinin eklenmesini desteklemez. Veri türleri eklemek için derleyicinin. pdb dosyasını yazma modunda açması gerekir.

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Geçerli hata ayıklama oturumunu sonlandırmadan bu hatayı kaldırmak için

1. Veri türünü hatadan önceki durumuna geri çevirin.

1. **Hata Ayıkla** menüsünde, **kod değişikliklerini Uygula**' yı seçin.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Kaynak kodunuzu değiştirmeden bu hatayı kaldırmak için

1. **Hata Ayıkla** menüsünden **hata ayıklamayı Durdur**' u seçin.

1. **Yapı** menüsünden **Oluştur**' u seçin.

Daha fazla bilgi için [desteklenen kod değişikliklerine](/visualstudio/debugger/supported-code-changes-cpp)bakın.
