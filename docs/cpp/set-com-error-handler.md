---
description: 'Hakkında daha fazla bilgi edinin: _set_com_error_handler'
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 88c59f30276089f28dc6e40b1ab5829bf68a7b4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116970"
---
# <a name="_set_com_error_handler"></a>_set_com_error_handler

COM hata işleme için kullanılan varsayılan işlevi değiştirir. **_set_com_error_handler** , Microsoft 'a özgüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
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

*sa*<br/>
HRESULT bilgileri.

*perrınfo*<br/>
`IErrorInfo` nesne.

## <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [_com_raise_error](../cpp/com-raise-error.md) tüm com hatalarını işler. Kendi hata işleme işlevinizi çağırmak için **_set_com_error_handler** kullanarak bu davranışı değiştirebilirsiniz.

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

**Üst bilgi:**\<comdef.h>

**LIB:** **/Zc: wchar_t** derleyici seçeneği belirtilmişse (varsayılan), comsuppw. lib veya comsuppwd. lib kullanın. **/Zc: wchar_t-** derleyici seçeneği belirtilmişse comsupp. lib kullanın. IDE 'de bu seçeneği ayarlama dahil daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM genel Işlevleri](../cpp/compiler-com-global-functions.md)
