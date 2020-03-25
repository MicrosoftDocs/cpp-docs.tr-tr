---
title: ConvertBSTRToString
ms.date: 11/04/2016
f1_keywords:
- ConvertBSTRToString
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
ms.openlocfilehash: 1d0ad8727dd4d5ec06a45ec26c67dd3ad268f524
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189536"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString

**Microsoft 'a özgü**

Bir `BSTR` değerini `char *`dönüştürür.

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

**Üstbilgi:** \<comutil. h >

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)
