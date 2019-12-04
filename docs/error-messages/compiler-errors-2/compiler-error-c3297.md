---
title: Derleyici hatası C3297
ms.date: 11/04/2016
f1_keywords:
- C3297
helpviewer_keywords:
- C3297
ms.assetid: 2a718b4c-6cdb-4418-92c0-fc3a259431c4
ms.openlocfilehash: 6fed01b0dcf50a657b6eb457ab8e546d0648beec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760107"
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
