---
description: 'Hakkında daha fazla bilgi edinin: _get_purecall_handler _set_purecall_handler'
title: _get_purecall_handler, _set_purecall_handler
ms.date: 11/04/2016
api_name:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_purecall_handler
- _set_purecall_handler_m
- set_purecall_handler_m
- set_purecall_handler
- stdlib/_set_purecall_handler
- stdlib/_get_purecall_handler
- _get_purecall_handler
helpviewer_keywords:
- _set_purecall_handler function
- set_purecall_handler function
- purecall_handler
- set_purecall_handler_m function
- _purecall_handler
- _set_purecall_handler_m function
- _get_purecall_handler function
ms.assetid: 2759b878-8afa-4129-86e7-72afc2153d9c
ms.openlocfilehash: 7971847c4ce0861db272ea3c722666b0ba0318d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339019"
---
# <a name="_get_purecall_handler-_set_purecall_handler"></a>_get_purecall_handler, _set_purecall_handler

Saf sanal işlev çağrısının hata işleyicisini alır veya ayarlar.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef void (__cdecl* _purecall_handler)(void);
_purecall_handler __cdecl _get_purecall_handler(void);
_purecall_handler __cdecl _set_purecall_handler(
   _purecall_handler function
);
```

### <a name="parameters"></a>Parametreler

*çalışmayacaktır*<br/>
Bir saf sanal işlev çağrıldığında çağrılacak işlev. **_Purecall_handler** işlev, void dönüş türüne sahip olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Önceki **_purecall_handler**. **`nullptr`** Önceki işleyici yoksa döndürür.

## <a name="remarks"></a>Açıklamalar

**_Get_purecall_handler** ve **_set_purecall_handler** işlevleri Microsoft 'A özgüdür ve yalnızca C++ kodu için geçerlidir.

Saf sanal işleve yapılan bir çağrı, bir uygulamaya sahip olmadığı için bir hatadır. Varsayılan olarak, derleyici, saf sanal bir işlev çağrıldığında bir hata işleyicisi işlevini çağırmak için kod üretir, bu da programı sonlandırır. Hata ayıklama veya raporlama amaçlarıyla yakalamak için, saf sanal işlev çağrıları için kendi hata işleyicisi işlevinizi yükleyebilirsiniz. Kendi hata işleyicinizi kullanmak için, **_purecall_handler** imzaya sahip bir işlev oluşturun ve sonra geçerli işleyici yapmak için **_set_purecall_handler** kullanın.

Her işlem için yalnızca bir **_purecall_handler** olduğundan, **_set_purecall_handler** çağırdığınızda tüm iş parçacıklarını hemen etkiler. Herhangi bir iş parçacığında son çağıran işleyiciyi ayarlar.

Varsayılan davranışı geri yüklemek için bir bağımsız değişken kullanarak **_set_purecall_handler** çağırın **`nullptr`** .

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_purecall_handler**, **_set_purecall_handler**|\<cstdlib> veya \<stdlib.h>|

Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// _set_purecall_handler.cpp
// compile with: /W1
#include <tchar.h>
#include <stdio.h>
#include <stdlib.h>

class CDerived;
class CBase
{
public:
   CBase(CDerived *derived): m_pDerived(derived) {};
   ~CBase();
   virtual void function(void) = 0;

   CDerived * m_pDerived;
};

class CDerived : public CBase
{
public:
   CDerived() : CBase(this) {};   // C4355
   virtual void function(void) {};
};

CBase::~CBase()
{
   m_pDerived -> function();
}

void myPurecallHandler(void)
{
   printf("In _purecall_handler.");
   exit(0);
}

int _tmain(int argc, _TCHAR* argv[])
{
   _set_purecall_handler(myPurecallHandler);
   CDerived myDerived;
}
```

```Output
In _purecall_handler.
```

## <a name="see-also"></a>Ayrıca bkz.

[Hata Işleme](../../c-runtime-library/error-handling-crt.md)<br/>
[_purecall](purecall.md)<br/>
