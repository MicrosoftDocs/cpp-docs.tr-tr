---
title: Derleyici Hatası C2220 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2220
dev_langs:
- C++
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7f4179b396e732ceeea20aeb9428d841a357a6d1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051327"
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