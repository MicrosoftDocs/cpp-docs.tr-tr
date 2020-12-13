---
description: 'Daha fazla bilgi edinin: ConvertBSTRToString'
title: ConvertBSTRToString
ms.date: 11/04/2016
f1_keywords:
- ConvertBSTRToString
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
ms.openlocfilehash: 72d6033003f186f358d9b4143498df65858ee354
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344620"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString

**Microsoft'a Özgü**

Bir `BSTR` değeri öğesine dönüştürür `char *` .

## <a name="syntax"></a>Sözdizimi

```
char* __stdcall ConvertBSTRToString(BSTR pSrc);
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
Bir BSTR değişkeni.

## <a name="remarks"></a>Açıklamalar

**Convertbstrtostring** , silmeniz gereken bir dize ayırır.

## <a name="example"></a>Örnek

```cpp
// ConvertBSTRToString.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")

int main() {
   BSTR bstrText = ::SysAllocString(L"Test");
   wprintf_s(L"BSTR text: %s\n", bstrText);

   char* lpszText2 = _com_util::ConvertBSTRToString(bstrText);
   printf_s("char * text: %s\n", lpszText2);

   SysFreeString(bstrText);
   delete[] lpszText2;
}
```

```Output
BSTR text: Test
char * text: Test
```

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comutil.h>

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM genel Işlevleri](../cpp/compiler-com-global-functions.md)
