---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2220'
title: Derleyici hatası C2220
ms.date: 11/04/2016
f1_keywords:
- C2220
helpviewer_keywords:
- C2220
ms.assetid: d610802c-64d7-40ad-a2a6-0ed0b6815a6c
ms.openlocfilehash: f45a34d0cdaa5e82c3f5e6c051126c6df4eb2005
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245440"
---
# <a name="compiler-error-c2220"></a>Derleyici hatası C2220

uyarı hata olarak değerlendirildi-nesne dosyası üretilmez

[/WX](../../build/reference/compiler-option-warning-level.md) derleyiciye tüm uyarıları hata olarak değerlendirmesine söyler. Bir hata oluştuğundan, nesne veya yürütülebilir dosya üretilmedi.

Bu hata yalnızca **/WX** bayrağı ayarlandığında ve derleme sırasında bir uyarı oluştuğunda görüntülenir. Bu hatayı gidermek için, projenizdeki tüm uyarıları ortadan kaldırmanız gerekir.

### <a name="to-fix-use-one-of-the-following-techniques"></a>Bu hatayı onarmak için, aşağıdaki tekniklerden birini kullanın

- Projenizde uyarılara neden olan sorunları giderin.

- Daha düşük bir uyarı düzeyinde derleyin — Örneğin, **/W4** yerine **/w3** kullanın.

- Belirli bir uyarıyı devre dışı bırakmak veya gizlemek için bir [Uyarı](../../preprocessor/warning.md) pragması kullanın.

- Derlemek için **/WX** kullanmayın.
