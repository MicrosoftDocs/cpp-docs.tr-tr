---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3297'
title: Derleyici hatası C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 39cbdfe6bbc19341c904d6bae90a71595f388400
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144605"
---
# <a name="compiler-error-c3297"></a>Derleyici hatası C3297

' constraint_2 ': ' constraint_1 ' kısıtlama olarak kullanılamaz, çünkü ' constraint_1 ' değer kısıtlamasına sahip

Değer sınıfları mühürlü. Bir kısıtlama bir değer sınıfınise, başka bir kısıtlama bundan böyle hiçbir şekilde türetilebilir.

Daha fazla bilgi için bkz. [genel tür parametrelerindeki kısıtlamalar (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3297 oluşturur.

```cpp
// C3297.cpp
// compile with: /clr /c
generic<class T, class U>
where T : value class
where U : T   // C3297
public ref struct R {};
```
