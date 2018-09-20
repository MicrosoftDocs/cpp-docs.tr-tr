---
title: swap işlevi (auto_gcroot) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- msclr::swap
- msclr.swap
dev_langs:
- C++
helpviewer_keywords:
- swap function
ms.assetid: 2fe8146b-a7f7-445a-9ae9-53b5556be701
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2606f49e4b8996d4e95abe91df9eb5c26d70929f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419418"
---
# <a name="swap-function-autogcroot"></a>swap İşlevi (auto_gcroot)

Bir arasında nesneleri değiştirir `auto_gcroot` ve başka bir.

## <a name="syntax"></a>Sözdizimi

```
template<typename _element_type>
void swap(
   auto_gcroot<_element_type> & _left,
   auto_gcroot<_element_type> & _right
);
```

#### <a name="parameters"></a>Parametreler

*_left*<br/>
Bir `auto_gcroot`.

*_right*<br/>
Başka bir `auto_gcroot`.

## <a name="example"></a>Örnek

```
// msl_swap_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s1 = "string one";
   auto_gcroot<String^> s2 = "string two";

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

**Üst bilgi dosyası** \<msclr\auto_gcroot.h >

**Namespace** msclr

## <a name="see-also"></a>Ayrıca Bkz.

[auto_gcroot](../dotnet/auto-gcroot.md)<br/>
[auto_gcroot::swap](../dotnet/auto-gcroot-swap.md)