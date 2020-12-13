---
description: 'Hakkında daha fazla bilgi edinin: _endthread _endthreadex'
title: _endthread, _endthreadex
ms.date: 4/2/2020
api_name:
- _endthread
- _endthreadex
- _o__endthread
- _o__endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
ms.openlocfilehash: ef74cac4cbe23a021ed8d796f92f2767695eb08e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332840"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

Bir iş parçacığını sonlandırır; **_endthread** , **_beginthread** tarafından oluşturulan bir iş parçacığını sonlandırır ve  **_endthreadex** **_beginthreadex** tarafından oluşturulan bir iş parçacığını sonlandırır.

## <a name="syntax"></a>Sözdizimi

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>Parametreler

*retval*<br/>
İş parçacığı çıkış kodu.

## <a name="remarks"></a>Açıklamalar

Bir iş parçacığını sonlandırmak için **_endthread** veya **_endthreadex** açıkça çağırabilirsiniz; Ancak, **_endthread** veya **_endthreadex** , iş parçacığı **_beginthread** veya **_beginthreadex** bir parametre olarak geçirilen yordamın döndürdüğü zaman otomatik olarak çağrılır. Bir iş parçacığını **endthread** veya **_endthreadex** çağrısıyla sonlandırmak, iş parçacığı için ayrılan kaynakların doğru kurtarılmasını sağlamaya yardımcı olur.

> [!NOTE]
> Libcmt. lib ile bağlantılı bir yürütülebilir dosya için Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API 'sini çağırmayın; Bu, çalışma zamanı sisteminin geri kazanma tarafından ayrılmış kaynaklardan yapılmasını önler. **_endthread** ve **_endthreadex** ayrılmış iş parçacığı kaynaklarını geri kazanın ve sonra **ExitThread**'i çağırın.

**_endthread** iş parçacığı tanıtıcısını otomatik olarak kapatır. (Bu davranış, Win32 **ExitThread** API 'sinden farklıdır.) Bu nedenle, **_beginthread** ve **_Endthread** kullandığınızda, Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API 'sini çağırarak iş parçacığı tanıtıcısını açıkça kapatmayın.

Win32 **ExitThread** API 'si gibi **_endthreadex** , iş parçacığı tanıtıcısını kapatmaz. Bu nedenle, **_beginthreadex** ve **_Endthreadex** kullandığınızda, Win32 **CloseHandle** API 'sini çağırarak iş parçacığı tanıtıcısını kapatmanız gerekir.

> [!NOTE]
> **_endthread** ve **_endthreadex** , iş parçacığında bekleyen C++ yıkıcılarının çağrılmamasına neden olur.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) çok iş parçacıklı sürümleri.

## <a name="example"></a>Örnek

[_Beginthread](beginthread-beginthreadex.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
