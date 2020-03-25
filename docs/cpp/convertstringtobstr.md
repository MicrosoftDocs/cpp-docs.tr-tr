---
title: ConvertStringToBSTR
ms.date: 11/04/2016
f1_keywords:
- ConvertStringToBSTR
helpviewer_keywords:
- ConvertStringToBSTR function
ms.assetid: 071f9b3b-9643-4e06-a1e5-de96ed15bab2
ms.openlocfilehash: 2065011ee6bbf98ce2c83be494f1e6631af9f7cf
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170715"
---
# <a name="convertstringtobstr"></a>ConvertStringToBSTR

**Microsoft 'a özgü**

Bir `char *` değerini `BSTR`dönüştürür.

## <a name="syntax"></a>Sözdizimi

```
BSTR __stdcall ConvertStringToBSTR(const char* pSrc)
```

#### <a name="parameters"></a>Parametreler

*pSrc*<br/>
`char *` değişken.

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

**Üstbilgi:** \<comutil. h >

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)
