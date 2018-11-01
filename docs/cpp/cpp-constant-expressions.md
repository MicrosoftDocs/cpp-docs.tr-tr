---
title: C++ Sabit İfadeleri
ms.date: 11/04/2016
helpviewer_keywords:
- constant expressions, syntax
- constant expressions
- expressions [C++], constant
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
ms.openlocfilehash: 97059066adadc3a7897cbd2c4c747e2a673e7201
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50576430"
---
# <a name="c-constant-expressions"></a>C++ Sabit İfadeleri

A *sabit* değeri olan bir değişikliğe neden olmaz. C++ iki anahtar sözcüğü bir nesne değiştirilecek ve o hedefi zorlamak için tasarlanmamıştır hedefi express olanak sağlar.

C++ sabit ifadeleri gerekir — bir sabit ifadeler — bildirimleri için:

- Dizi sınırları

- Case deyimleri Seçici

- Bit alanı uzunluğu belirtimi

- Sabit listesi başlatıcıları

Sabit ifadelerde yasal yalnızca işlenen şunlardır:

- Sabit değerler

- Numaralandırma sabitlerini

- Değerleri, sabit ifadeler başlatılır const olarak bildirildi

- **sizeof** ifadeleri

Nonintegral Sabitleri (açıkça veya dolaylı olarak) sabit bir ifadede meşru integral türlerine dönüştürülmesi gerekir. Bu nedenle, aşağıdaki kod geçerlidir:

```cpp
const double Size = 11.0;
char chArray[(int)Size];
```

Açık dönüştürmeler integral türleri sabit ifadelerde geçerli; diğer tüm türleri ve türetilen türler için işlenen olarak kullanılması dışında geçersiz **sizeof** işleci.

Virgül işleci ve atama işleçleri sabit ifadelerde kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[İfade Türleri](../cpp/types-of-expressions.md)