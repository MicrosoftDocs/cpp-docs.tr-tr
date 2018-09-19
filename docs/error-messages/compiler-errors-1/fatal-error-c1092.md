---
title: Önemli hata C1092 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1092
dev_langs:
- C++
helpviewer_keywords:
- C1092
ms.assetid: bcaa87f0-fbfc-4a33-844b-3b9f5d67f279
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9852b7b3d695d5414e52727ce672ee3258f6840b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46077158"
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