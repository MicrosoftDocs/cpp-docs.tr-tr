---
title: _set_com_error_handler | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 52258c64c98651fc7a962c2a246fe8bde79d8ab8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setcomerrorhandler"></a>_set_com_error_handler
**Microsoft özel**  
  
 COM hata işleme için kullanılan varsayılan işlevi değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void __stdcall _set_com_error_handler(  
   void (__stdcall *pHandler)(  
      HRESULT hr,   
      IErrorInfo* perrinfo  
   )  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pHandler`  
 Değiştirme işlevinin işaretçisi.  
  
 `hr`  
 `HRESULT` bilgileri.  
  
 `perrinfo`  
 `IErrorInfo`nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, [_com_raise_error](../cpp/com-raise-error.md) tüm COM hatalarını ele alır. Bu davranışı, kendi hata işleme işlevinizi çağırmak için `_set_com_error_handler` kullanarak değiştirebilirsiniz.  
  
 Değiştirme işlevi, `_com_raise_error` öğesinin imzasına eşdeğer olan bir imza içermelidir.  
  
## <a name="example"></a>Örnek  
  
```  
// _set_com_error_handler.cpp  
// compile with /EHsc  
#include <stdio.h>  
#include <comdef.h>  
#include <comutil.h>  
  
// Importing ado dll to attempt to establish an ado connection.  
// Not related to _set_com_error_handler   
#import "C:\Program Files\Common Files\System\ado\msado15.dll" no_namespace rename("EOF", "adoEOF")  
  
void __stdcall _My_com_raise_error(HRESULT hr, IErrorInfo* perrinfo)  
{  
   throw "Unable to establish the connection!";  
}  
  
int main()  
{  
   _set_com_error_handler(_My_com_raise_error);  
   _bstr_t bstrEmpty(L"");  
   _ConnectionPtr Connection = NULL;  
   try  
   {  
      Connection.CreateInstance(__uuidof(Connection));  
      Connection->Open(bstrEmpty, bstrEmpty, bstrEmpty, 0);   
   }  
   catch(char* errorMessage)  
   {  
      printf("Exception raised: %s\n", errorMessage);  
   }  
  
   return 0;  
}  
```  
  
```Output  
Exception raised: Unable to establish the connection!  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** comdef.h  
  
 **LIB:** varsa **wchar_t yerel tür olan** derleyici seçeneği üzerinde comsuppw.lib veya comsuppwd.lib kullanın. Varsa **wchar_t yerel tür olan** kapalı ise comsupp.lib kullanın. Daha fazla bilgi için bkz: [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Global COM işlevleri](../cpp/compiler-com-global-functions.md)