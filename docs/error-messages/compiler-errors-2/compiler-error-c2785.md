---
title: Derleyici Hatası C2785
ms.date: 11/04/2016
f1_keywords:
- C2785
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
ms.openlocfilehash: fcf2bbb01f2aac668ff52884a6ccfb36c66aa89d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445846"
---
# <a name="compiler-error-c2785"></a>Derleyici Hatası C2785

'declaration1' ve 'declaration2' farklı dönüş türlerine sahip

İşlev şablonu uzmanlığı dönüş türünün birincil işlev şablonu dönüş türünden farklıdır.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Tüm tutarlılık için işlev şablonunun uzmanlıkları denetleyin.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2785 oluşturur:

```
// C2785.cpp
// compile with: /c
template<class T> void f(T);

template<> int f(int); // C2785
template<> void f(int); // OK
```