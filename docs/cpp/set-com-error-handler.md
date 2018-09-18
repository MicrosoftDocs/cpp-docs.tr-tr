---
title: _set_com_error_handler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 192707fe15560adb816b530ecf0e67713ae7d302
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46092563"
---
# <a name="setcomerrorhandler"></a>_set_com_error_handler

**Microsoft'a özgü**

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

*pHandler*<br/>
Değiştirme işlevinin işaretçisi.

*İK*<br/>
HRESULT bilgileri.

*perrinfo*<br/>
`IErrorInfo` nesne.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [_com_raise_error](../cpp/com-raise-error.md) tüm COM hatalarını işler. Kullanarak bu davranışı değiştirebilirsiniz **_set_com_error_handler** kendi hata işleme işlevinizi çağırmak için.

Değiştirme işlevi, `_com_raise_error` öğesinin imzasına eşdeğer olan bir imza içermelidir.

## <a name="example"></a>Örnek

```cpp
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

**Başlık:** \<comdef.h >

**Lib:** varsa **wchar_t yerel tür olan** derleyici seçeneği açıktır, comsuppw.lib veya comsuppwd.lib kullanın. Varsa **wchar_t yerel tür olan** kapalıysa, comsupp.lib kullanın. Daha fazla bilgi için [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)