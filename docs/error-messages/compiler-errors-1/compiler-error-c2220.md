---
title: Derleyici Hatası C2220
ms.date: 11/04/2016
f1_keywords:
- C2220
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
ms.openlocfilehash: 3ff730c6fea7d2c57c4ec3054fc627cdc6227e2d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603417"
---
# <a name="compiler-error-c2220"></a>Derleyici Hatası C2220

Uyarı - nesne dosyası hata olarak değerlendirildi

[/WX](../../build/reference/compiler-option-warning-level.md) derleyiciye tüm uyarıları hata olarak değerlendir. Bir hata oluştuğundan, nesne veya yürütülebilir dosya oluşturuldu.

Bu hata yalnızca görüntülenir **wx** bayrağı ayarlı olup derleme sırasında bir uyarı gerçekleşir. Bu hatayı düzeltmek için projenizdeki her uyarıyı ortadan kaldırmanız gerekir.

### <a name="to-fix-use-one-of-the-following-techniques"></a>Düzeltmek için aşağıdaki tekniklerden birini kullanın:

- Projenizde uyarıları neden sorunları giderin.

- Daha düşük bir uyarı düzeyinde derleyin — Örneğin, **/W3** yerine **/W4**.

- Kullanım bir [uyarı](../../preprocessor/warning.md) devre dışı bırakmak veya belirli bir uyarıyı bastırmak pragması.

- Kullanmayın **wx** derlemek için.