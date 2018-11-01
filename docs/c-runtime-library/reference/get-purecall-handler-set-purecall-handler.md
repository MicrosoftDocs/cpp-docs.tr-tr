---
title: _get_purecall_handler, _set_purecall_handler
ms.date: 11/04/2016
apiname:
- _set_purecall_handler
- _set_purecall_handler_m
- _get_purecall_handler
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 0009b4bc1c7bf70bd84b9a82ecdc8643789e8164
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50646374"
---
# <a name="getpurecallhandler-setpurecallhandler"></a>_get_purecall_handler, _set_purecall_handler

Alır veya ayarlar saf sanal işlev çağrısı için hata işleyicisi.

## <a name="syntax"></a>Sözdizimi

```cpp
typedef void (__cdecl* _purecall_handler)(void);
_purecall_handler __cdecl _get_purecall_handler(void);
_purecall_handler __cdecl _set_purecall_handler(
   _purecall_handler function
);
```

### <a name="parameters"></a>Parametreler

*İşlevi*<br/>
Saf sanal işlev çağrıldığında çağrılacak işlev. A **_purecall_handler** işlevin dönüş türü void olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Önceki **_purecall_handler**. Döndürür **nullptr** olduğunda önceki işleyici yok.

## <a name="remarks"></a>Açıklamalar

**_Get_purecall_handler** ve **_set_purecall_handler** işlevleri Microsoft'a özgü olan ve yalnızca C++ kodu için geçerlidir.

Uygulaması olduğundan saf sanal işlev çağrısı bir hata var. Varsayılan olarak, derleyici program sona erer saf sanal işlevi çağrıldığında bir hata işleyicisi işlevini çağırmak için kod oluşturur. Hata ayıklama veya raporlama amacıyla bunları yakalamak için saf sanal işlev çağrıları, kendi hata işleyici işlevi yükleyebilirsiniz. Kendi hata işleyicisi kullanacak şekilde sahip bir işlev oluşturma **_purecall_handler** imzası, ardından **_set_purecall_handler** geçerli işleyici yapma.

Olmadığı için yalnızca bir **_purecall_handler** çağırdığınızda her işlem için **_set_purecall_handler** hemen tüm iş parçacıklarını etkiler. Son çağrı herhangi bir iş parçacığı üzerinde işleyici ayarlar.

Varsayılan davranışı geri yüklemek için çağrı **_set_purecall_handler** kullanarak bir **nullptr** bağımsız değişken.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_purecall_handler**, **_set_purecall_handler**|\<cstdlib > veya \<stdlib.h >|

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

[Hata İşleme](../../c-runtime-library/error-handling-crt.md)<br/>
[_purecall](purecall.md)<br/>
