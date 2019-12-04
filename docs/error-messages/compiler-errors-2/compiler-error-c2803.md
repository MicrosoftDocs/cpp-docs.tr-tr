---
title: Derleyici hatası C2803
ms.date: 11/04/2016
f1_keywords:
- C2803
helpviewer_keywords:
- C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
ms.openlocfilehash: d39f737ba02f3fa9c9d5f61594ddf730db6739a5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760666"
---
# <a name="compiler-error-c2803"></a>Derleyici hatası C2803

' işleç işleci ', sınıf türünde en az bir biçimsel parametreye sahip olmalıdır

Aşırı yüklenmiş işlecin sınıf türünde bir parametresi eksik.

Başvuruya göre en az bir parametre geçirmeniz gerekir (işaretçiler, ancak başvurular kullanmayın) ya da değere göre, "a < b" (a ve b türünde bir a ve b) yazabiliyor.

Her iki parametre de işaretçisiyse, işaretçi adreslerinin saf bir karşılaştırması olur ve Kullanıcı tanımlı dönüştürmeyi kullanmaz.

Aşağıdaki örnek C2803 oluşturur:

```cpp
// C2803.cpp
// compile with: /c
class A{};
bool operator< (const A *left, const A *right);   // C2803
// try the following line instead
// bool operator< (const A& left, const A& right);
```
