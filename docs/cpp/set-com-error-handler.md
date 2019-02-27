---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 864236e86b4aeb6ce7b3315df57af1b577693c26
ms.sourcegitcommit: f127b08f114b8d6cab6b684febcb6f2ae0e055ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/27/2019
ms.locfileid: "56954945"
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

**Lib:** Varsa **/ZC: wchar_t** derleyici seçeneği belirtilmemişse (varsayılan), comsuppw.lib veya comsuppwd.lib kullanın. Varsa **/Zc:wchar_t-** derleyici seçeneği belirtilmemişse, comsupp.lib kullanın. Bu seçenek IDE içinde ayarlama dahil olmak üzere daha fazla bilgi için bkz. [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)
