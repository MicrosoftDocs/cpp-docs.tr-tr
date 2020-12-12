---
description: 'Hakkında daha fazla bilgi edinin: sanal işlevi geçersiz kılma'
title: Sanal işlevi geçersiz kılma
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.virtualfunc.override
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
ms.openlocfilehash: d4c800006d5227ed5397c17284c03968a24a3964
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335915"
---
# <a name="override-a-virtual-function"></a>Sanal işlevi geçersiz kılma

Visual Studio [Özellikler penceresi](/visualstudio/ide/reference/properties-window)bir temel sınıfta tanımlanan sanal işlevleri geçersiz kılabilirsiniz.

**Özellikler penceresi bir sanal işlevi geçersiz kılmak için:**

1. Sınıf Görünümü ' de sınıfı seçin.

1. Özellikler penceresi, **geçersiz kılmalar** düğmesini seçin.

   > [!NOTE]
   > **Geçersiz kılmalar** düğmesi, sınıf görünümü sınıf adını seçtiğinizde ya da kaynak pencere içinde seçerken kullanılabilir.

   Sol sütun sanal işlevleri listeler. Bir sanal işlevin adı sağ sütunda da görünüyorsa, bir geçersiz kılma zaten uygulanmıştır.

1. İşlevin geçersiz kılma işlemi yoksa, işlev geçersiz kılmanın önerilen adını funcname olarak göstermek için Özellikler penceresi sağ sütunundaki hücreyi seçin \<add> .

1. İşlev için saplama kodu eklemek üzere önerilen adı seçin.

1. Geçersiz kılma işlevini düzenlemek için, Sınıf Görünümü işlevindeki işlevin adına çift tıklayın ve kodu kaynak penceresinde düzenleyin.

Bir geçersiz kılmayı kaldırmak için, sağ sütundaki işlev adını geçersiz kıl ' ı seçin ve \<delete> *funcname*' yi seçin. İşlevin kodu açıklama yazdı.
