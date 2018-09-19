---
title: Derleyici Hatası C2803 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2803
dev_langs:
- C++
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7885735ebad1ff90afaf4ba8eaf6dfca9f3e0ab3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027047"
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