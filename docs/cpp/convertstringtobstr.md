---
description: 'Daha fazla bilgi edinin: ConvertStringToBSTR'
title: ConvertStringToBSTR
ms.date: 11/04/2016
f1_keywords:
- ConvertStringToBSTR
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
ms.openlocfilehash: 7348fdec3448d17b51fd77385297422a8f10fd05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344607"
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR

**Microsoft'a Özgü**

Bir `char *` değeri öğesine dönüştürür `BSTR` .

## <a name="syntax"></a>Sözdizimi

```
BSTR __stdcall ConvertStringToBSTR(const char* pSrc)
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
Bir `char *` değişken.

## <a name="example"></a>Örnek

```cpp
// ConvertStringToBSTR.cpp
#include <comutil.h>
#include <stdio.h>

#pragma comment(lib, "comsuppw.lib")
#pragma comment(lib, "kernel32.lib")

int main() {
   char* lpszText = "Test";
   printf_s("char * text: %s\n", lpszText);

   BSTR bstrText = _com_util::ConvertStringToBSTR(lpszText);
   wprintf_s(L"BSTR text: %s\n", bstrText);

   SysFreeString(bstrText);
}
```

```Output
char * text: Test
BSTR text: Test
```

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comutil.h>

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM genel Işlevleri](../cpp/compiler-com-global-functions.md)
