---
title: Derleyici Hatası C2461 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39d58b315fdd7e3c4e1899041cebf8400813ed40
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46029305"
---
# <a name="compiler-error-c2461"></a>Derleyici Hatası C2461

> '*sınıfı*': Oluşturucu sözdiziminde biçimsel parametreler eksik

Sınıf için oluşturucu herhangi bir biçimsel parametre belirtmiyor. Bir oluşturucu bildirimi bir biçimsel parametre listesi belirtmelisiniz. Liste boş olabilir.

Bu sorunu gidermek için bildirimi sonra parantez çifti Ekle *sınıfı*:: **sınıfı*.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2461 düzeltme işlemi gösterilmektedir:

```cpp
// C2461.cpp
// compile with: /c
class C {
   C::C;     // C2461
   C::C();   // OK
};
```