---
description: 'Daha fazla bilgi edinin: Swap Işlevi (auto_handle)'
title: swap İşlevi (auto_handle)
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- swap function
ms.assetid: 7dd91b5c-f0de-4634-a2e2-642626706e27
ms.openlocfilehash: 24e3ad0d80cb747ddff116682cb9760b29ccc893
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335293"
---
# <a name="swap-function-auto_handle"></a>swap İşlevi (auto_handle)

Nesneleri bir `auto_handle` ve diğeri arasında değiştirir.

## <a name="syntax"></a>Sözdizimi

```
template<typename _element_type>
void swap(
   auto_handle<_element_type> % _left,
   auto_handle<_element_type> % _right
);
```

#### <a name="parameters"></a>Parametreler

*_left*<br/>
Bir `auto_handle` .

*_right*<br/>
Başka bir `auto_handle` .

## <a name="example"></a>Örnek

```cpp
// msl_swap_auto_handle.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1 = "string one";
   auto_handle<String> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   swap( s1, s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası**\<msclr\auto_handle.h>

**Ad alanı** msclr

## <a name="see-also"></a>Ayrıca bkz.

[auto_handle](../dotnet/auto-handle.md)<br/>
[auto_handle::swap](./auto-handle-class.md#swap)
