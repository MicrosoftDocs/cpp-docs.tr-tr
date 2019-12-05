---
title: _set_com_error_handler
ms.date: 11/04/2016
helpviewer_keywords:
- _set_com_error_handler function
ms.assetid: 49fe4fca-5e37-4d83-abaf-15be5ce37f94
ms.openlocfilehash: 226dce24de68edd66ca68c43e41ce0cb5b8a1b48
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857300"
---
# <a name="_set_com_error_handler"></a>_set_com_error_handler

COM hata işleme için kullanılan varsayılan işlevi değiştirir. **_set_com_error_handler** , Microsoft 'a özgüdür.

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

*HR*<br/>
HRESULT bilgileri.

*perrınfo*<br/>
`IErrorInfo` nesnesi.

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

**Üstbilgi:** \<Comdef. h >

**LIB:** **/Zc: wchar_t** derleyici seçeneği belirtilmişse (varsayılan), comsuppw. lib veya comsuppwd. lib kullanın. **/Zc: wchar_t-** derleyici seçeneği belirtilmişse comsupp. lib kullanın. IDE 'de bu seçeneği ayarlama dahil daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)
