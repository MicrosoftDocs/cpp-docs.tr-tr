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
ms.openlocfilehash: db1f512b10bdedffa5b6978b735c881dc21370ce
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406708"
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
 **Başlık:** \<comutil.h >.  
  
 **Lib:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)