---
title: ConvertBSTRToString | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- ConvertBSTRToString
dev_langs:
- C++
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e84b8fb27c926a4b61ae631638ea4708fcf538b7
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463996"
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString
**Microsoft'a özgü**  
  
 Dönüştürür bir `BSTR` değerini bir `char *`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char* __stdcall ConvertBSTRToString(BSTR pSrc);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pSrc*  
 BSTR değişken.  
  
## <a name="remarks"></a>Açıklamalar  
 **ConvertBSTRToString** silmelisiniz bir dize ayırır.  
  
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
  
**END Microsoft özgü**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comutil.h >  
  
 **Lib:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)