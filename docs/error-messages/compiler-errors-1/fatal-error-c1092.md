---
title: Önemli hata C1092
ms.date: 11/04/2016
f1_keywords:
- C1092
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
ms.openlocfilehash: 3268e5b124be40313bdc97b4c95d935ddd4f9160
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462744"
---
# <a name="fatal-error-c1092"></a>Önemli hata C1092

Düzenle ve devam et değişiklikleri veri türlerini desteklemez; gerekli derleme

Değiştirdiğiniz ya da bir veri türü, son başarılı yapıdan beri eklenmiş.

- Düzenle ve devam et, sınıf, yapı veya sabit listesi tanımlarını dahil olmak üzere mevcut veri türleri için değişiklikleri desteklemez. Hata ayıklamayı durdurmak ve uygulamayı oluşturmak gerekir.

- Düzenle ve devam et, yeni bir program veritabanı dosyası varsa, vc gibi veri türlerinin eklenmesini desteklemez*x*0. pdb (burada *x* önemli Visual C++ sürümü kullanılıyor) salt okunur. Veri türleri eklemek için derleyicinin yazma modunda .pdb dosyasını açmanız gerekir.

### <a name="to-remove-this-error-without-ending-the-current-debug-session"></a>Bu hata, geçerli hata ayıklama oturumu sona erdirmeden kaldırmak için

1. Hata öncesinde durumuna geri dön veri türünü değiştirin.

1. Gelen **hata ayıklama** menüsünde seçin **kod değişikliklerini uygulama**.

### <a name="to-remove-this-error-without-changing-your-source-code"></a>Bu hata, kaynak kodunuzda değişiklik yapmadan kaldırmak için

1. Gelen **hata ayıklama** menüsünde seçin **hata ayıklamayı Durdur**.

1. Gelen **derleme** menüsünde seçin **yapı**.

Daha fazla bilgi için bkz: [desteklenen kod değişiklikleri](/visualstudio/debugger/supported-code-changes-cpp).