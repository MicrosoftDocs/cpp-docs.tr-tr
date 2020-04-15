---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: c76f479255080400e07678ef5dbde572b7a9dffc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348033"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

İş parçacığı sonlandırır; **_endthread,** **_beginthread** tarafından oluşturulan bir iş parçacığına son ve **_beginthreadex** **tarafından**oluşturulan bir iş parçacığının _endthreadex sonlandırır.

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

İş parçacığına son vermek için **_endthread** veya **_endthreadex** açıkça arayabilirsiniz; ancak, iş parçacığı **_beginthread** veya **_beginthreadex**parametre olarak geçirildiğinde, **_endthread** veya **_endthreadex** otomatik olarak çağrılır. İş **parçacığının son iş parçacığı** veya **_endthreadex** için bir çağrıyla sonlandırması, iş parçacığı için ayrılan kaynakların düzgün kurtarılmasını sağlamaya yardımcı olur.

> [!NOTE]
> Libcmt.lib ile bağlantılı çalıştırılabilir bir dosya için Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API'yi aramayın; bu, çalışma zamanı sisteminin ayrılan kaynakları geri geri almasını engeller. **_endthread** ve **_endthreadex** ayrılan iş parçacığı kaynaklarını geri almak ve sonra **ExitThread**arayın.

**_endthread** iş parçacığı tutamacını otomatik olarak kapatır. (Bu davranış Win32 **ExitThread** API farklıdır.) Bu nedenle, **_beginthread** ve **_endthread**kullandığınızda, Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API'yi arayarak iş parçacığı tutamacını açıkça kapatmayın.

Win32 **ExitThread** API gibi, **_endthreadex** iş parçacığı tutamacını kapatmaz. Bu nedenle, **_beginthreadex** ve **_endthreadex**kullandığınızda, Win32 **CloseHandle** API'yi arayarak iş parçacığı tutamacını kapatmanız gerekir.

> [!NOTE]
> **_endthread** ve **_endthreadex,** diş parçacığının çağrılmamasını bekleyen C++ yıkıcılarına neden olur.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_endthread**|\<process.h>|
|**_endthreadex**|\<process.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

Yalnızca C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) çok iş parçacığı sürümleri.

## <a name="example"></a>Örnek

[_beginthread](beginthread-beginthreadex.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
