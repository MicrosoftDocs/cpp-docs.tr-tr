---
title: Derleyici Hatası C2825 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2825
dev_langs:
- C++
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bd0e9f8f2f5444b8835abc9f6802919f0e6c941
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117588"
---
# <a name="compiler-error-c2825"></a>Derleyici Hatası C2825

var: bir sınıf ya da ardından, ad alanı olmalıdır '::'

Başarısız bir tam adı oluşturmak için girişimde bulunuldu.

Örneğin, kodunuzu nereye işlev adı ile başlayan bir işlev bildirimi içermediğinden emin emin::.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2825 oluşturur:

```
// C2825.cpp
typedef int i;
int main() {
   int* p = new int;
   p->i::i();   // C2825
   // try the following line instead
   // p->i::~i();
}
```