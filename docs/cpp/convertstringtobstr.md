---
title: ConvertStringToBSTR
ms.date: 11/04/2016
f1_keywords:
- ConvertStringToBSTR
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
ms.openlocfilehash: 5e7d8abd29033fc88dae1e83fcc6467fb0ace46f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485390"
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR

**Microsoft'a özgü**

Dönüştürür bir `char *` değerini bir `BSTR`.

## <a name="syntax"></a>Sözdizimi

```
BSTR __stdcall ConvertStringToBSTR(const char* pSrc)
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
A `char *` değişkeni.

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

**END Microsoft özgü**

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<comutil.h >

**Lib:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)