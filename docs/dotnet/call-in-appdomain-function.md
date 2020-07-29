---
title: call_in_appdomain İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- call_in_appdomain
helpviewer_keywords:
- call_in_appdomain function
ms.assetid: 9a1a5026-b76b-4cae-a3d4-29badeb9db9c
ms.openlocfilehash: 567b6d8fe9412e58f21de9a1031ec54c4bc01cdc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230902"
---
# <a name="call_in_appdomain-function"></a>call_in_appdomain İşlevi

Belirtilen uygulama etki alanında bir işlevi yürütür.

## <a name="syntax"></a>Söz dizimi

```
template <typename ArgType1, ...typename ArgTypeN>
void call_in_appdomain(
   DWORD appdomainId,
   void (*voidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
template <typename RetType, typename ArgType1, ...typename ArgTypeN>
RetType call_in_appdomain(
   DWORD appdomainId,
   RetType (*nonvoidFunc)(ArgType1, ...ArgTypeN) [ ,
   ArgType1 arg1,
   ...
   ArgTypeN argN ]
);
```

#### <a name="parameters"></a>Parametreler

*AppDomainID*<br/>
İşlevin çağrılacak AppDomain.

*voidFunc*<br/>
**`void`** N parametresi alan bir işlev işaretçisi (0 <= N <= 15).

*nonvoidFunc*<br/>
**`void`** N parametresi alan işlev olmayan bir işaretçi (0 <= N <= 15).

*arg1... argN*<br/>
`voidFunc`Diğer AppDomain 'e veya diğer AppDomain 'e geçirilecek sıfır-15 parametre `nonvoidFunc` .

## <a name="return-value"></a>Dönüş Değeri

`voidFunc` `nonvoidFunc` Belirtilen uygulama etki alanında veya yürütmenin sonucu.

## <a name="remarks"></a>Açıklamalar

Geçirilen işlevin bağımsız değişkenlerinin `call_in_appdomain` clr türleri olmaması gerekir.

## <a name="example"></a>Örnek

```cpp
// msl_call_in_appdomain.cpp
// compile with: /clr

// Defines two functions: one takes a parameter and returns nothing,
// the other takes no parameters and returns an int.  Calls both
// functions in the default appdomain and in a newly-created
// application domain using call_in_appdomain.

#include <msclr\appdomain.h>

using namespace System;
using namespace msclr;

void PrintCurrentDomainName( char* format )
{
   String^ s = gcnew String(format);
   Console::WriteLine( s, AppDomain::CurrentDomain->FriendlyName );
}

int GetDomainId()
{
   return AppDomain::CurrentDomain->Id;
}

int main()
{
   AppDomain^ appDomain1 = AppDomain::CreateDomain( "First Domain" );

   call_in_appdomain( AppDomain::CurrentDomain->Id,
                   &PrintCurrentDomainName,
                   (char*)"default appdomain: {0}" );
   call_in_appdomain( appDomain1->Id,
                   &PrintCurrentDomainName,
                   (char*)"in appDomain1: {0}" );

   int id;
   id = call_in_appdomain( AppDomain::CurrentDomain->Id, &GetDomainId );
   Console::WriteLine( "default appdomain id = {0}", id );
   id = call_in_appdomain( appDomain1->Id, &GetDomainId );
   Console::WriteLine( "appDomain1 id = {0}", id );
}
```

## <a name="output"></a>Çıktı

```
default appdomain: msl_call_in_appdomain.exe
in appDomain1: First Domain
default appdomain id = 1
appDomain1 id = 2
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası**\<msclr\appdomain.h>

**Ad alanı** msclr
