---
title: Derleyici Hatası C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d20b8dde9f4134273adcba0f947f685f7ce7d213
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447274"
---
# <a name="compiler-error-c2803"></a>Derleyici Hatası C2803

'operator işleci' sınıf türü en az bir biçimsel parametreye sahip olmalıdır

Aşırı yüklenmiş işleç sınıf türünde bir parametre eksik.

Başvuru (işaretçiler ve başvurular kullanarak değil) veya yazılabilmesi için değer en az bir parametre geçirmek gereken "bir < b" (bir ve türü sınıf A b verilen).

Her iki parametre işaretçiyse işaretçi adreslerine saf karşılaştırması olacak ve kullanıcı tanımlı dönüştürme kullanmaz.

Aşağıdaki örnek, C2803 oluşturur:

```
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```