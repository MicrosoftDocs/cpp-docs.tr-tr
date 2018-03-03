---
title: ConvertBSTRToString | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- ConvertBSTRToString
dev_langs:
- C++
helpviewer_keywords:
- ConvertBSTRToString function
ms.assetid: ab6ce555-3d75-4e9c-9cb8-ada6d8ce43b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a7f3463e34c17bcde4f64b89e1ae083228317293
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="convertbstrtostring"></a>ConvertBSTRToString
**Microsoft Specific**  
  
 Dönüştüren bir `BSTR` değeri bir **char \*** .  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      char* __stdcall ConvertBSTRToString(  
   BSTR pSrc  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pSrc`  
 BSTR değişken.  
  
## <a name="remarks"></a>Açıklamalar  
 `ConvertBSTRToString`bir dize silmeniz gerekir ayırır.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
**SON Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comutil.h >.  
  
 **LIB:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)