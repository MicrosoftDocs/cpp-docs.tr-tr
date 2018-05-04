---
title: Derleyici Uyarısı (Düzey 3) C4373 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- C4373
dev_langs:
- C++
helpviewer_keywords:
- C4373
ms.assetid: 670c0ba3-b7d6-4aed-b207-1cb84da3bcde
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1694c8d15ad65b39a27af8ae5aae02e9c729896
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="compiler-warning-level-3-c4373"></a>Derleyici Uyarısı (Düzey 3) C4373

> '*işlevi*': sanal işlevi geçersiz kılma işlemleri*base_function*', önceki sürümlerini derleyici parametreleri yalnızca const/volatile niteleyicileri tarafından farklıydı olduğunda geçersiz

## <a name="remarks"></a>Açıklamalar

Uygulamanızı bir taban sınıf içinde sanal yöntemini geçersiz kılar türetilmiş bir sınıf yönteminde içerir ve yalnızca geçersiz kılma yöntemi parametrelerinde tarafından farklı bir [const](../../cpp/const-cpp.md) veya [volatile](../../cpp/volatile-cpp.md) gelen niteleyicisi sanal bir yöntem parametreleri. Bu derleyici yöntemine yapılan bir işlev başvurusu ya da temel bağlamanız gerekir veya türetilmiş sınıf anlamına gelir.

Visual Studio 2008 önce derleyici sürümler yöntemi temel sınıf işlevi bağlamak ve ardından bir uyarı iletisi yayınlar. Derleyici sonraki sürümleri Yoksay `const` veya `volatile` Niteleyici, türetilmiş sınıf yönteminde işlevi bağlamak ve ardından uyarı vermek **C4373**. Bu ikinci davranış C++ standart ile uyumludur.

## <a name="example"></a>Örnek

Aşağıdaki kod örneğinde C4373 uyarı oluşturur. Bu sorunu çözmek için aynı MS niteleyicileri temel üye işlevini geçersiz kılma ya da yapabilir veya olmayan bir geçersiz kılma oluşturun istiyordunuz, türetilmiş sınıf işlevinde farklı bir ad verebilir.

```cpp
// c4373.cpp
// compile with: /c /W3
#include <stdio.h>
struct Base
{
    virtual void f(int i) {
        printf("base\n");
    }
};

struct Derived : Base
{
    void f(const int i) {  // C4373
        printf("derived\n");
    }
};

void main()
{
    Derived d;
    Base* p = &d;
    p->f(1);
}
```

```Output
derived
```