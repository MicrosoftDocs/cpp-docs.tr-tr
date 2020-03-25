---
title: Derleyici hatası C2220
ms.date: 11/04/2016
f1_keywords:
- C2220
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
ms.openlocfilehash: c4fdac833e69e748dd29b9cf772c167fc1dbbd00
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206667"
---
# <a name="compiler-error-c2220"></a>Derleyici hatası C2220

uyarı hata olarak değerlendirildi-nesne dosyası üretilmez

[/WX](../../build/reference/compiler-option-warning-level.md) derleyiciye tüm uyarıları hata olarak değerlendirmesine söyler. Bir hata oluştuğundan, nesne veya yürütülebilir dosya üretilmedi.

Bu hata yalnızca **/WX** bayrağı ayarlandığında ve derleme sırasında bir uyarı oluştuğunda görüntülenir. Bu hatayı gidermek için, projenizdeki tüm uyarıları ortadan kaldırmanız gerekir.

### <a name="to-fix-use-one-of-the-following-techniques"></a>Bu hatayı onarmak için, aşağıdaki tekniklerden birini kullanın

- Projenizde uyarılara neden olan sorunları giderin.

- Daha düşük bir uyarı düzeyinde derleyin — Örneğin, **/W4**yerine **/w3** kullanın.

- Belirli bir uyarıyı devre dışı bırakmak veya gizlemek için bir [Uyarı](../../preprocessor/warning.md) pragması kullanın.

- Derlemek için **/WX** kullanmayın.
