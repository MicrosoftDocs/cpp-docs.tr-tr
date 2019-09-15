---
title: _endthread, _endthreadex
ms.date: 11/04/2016
api_name:
- _endthread
- _endthreadex
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
ms.openlocfilehash: c9dd4a49e534e8fa3e0f5ac735faccb4b0f65af5
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70937730"
---
# <a name="_endthread-_endthreadex"></a>_endthread, _endthreadex

Bir iş parçacığını sonlandırır; **_endthread** , **_beginthread** ve **_endthreadex** tarafından oluşturulan bir iş parçacığını, **_beginthreadex**tarafından oluşturulan bir iş parçacığını sonlandırır.

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

Bir iş parçacığını sonlandırmak için **_endthread** veya **_endthreadex** öğesini açıkça çağırabilirsiniz; Ancak, iş parçacığı **_beginthread** veya **_beginthreadex**'e parametre olarak geçirilen yordamın döndürdüğü zaman **_endthread** veya **_endthreadex** otomatik olarak çağrılır. **Endthread** veya **_endthreadex** çağrısıyla bir iş parçacığını sonlandırmak, iş parçacığı için ayrılan kaynakların doğru şekilde kurtarılmasını sağlamaya yardımcı olur.

> [!NOTE]
> Libcmt. lib ile bağlantılı bir yürütülebilir dosya için Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API 'sini çağırmayın; Bu, çalışma zamanı sisteminin geri kazanma tarafından ayrılmış kaynaklardan yapılmasını önler. **_endthread** ve **_endthreadex** ayrılan iş parçacığı kaynaklarını geri kazanın ve sonra **ExitThread**'i çağırır.

**_endthread** iş parçacığı tanıtıcısını otomatik olarak kapatır. (Bu davranış, Win32 **ExitThread** API 'sinden farklıdır.) Bu nedenle, **_beginthread** ve **_Endthread**kullandığınızda, Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API 'sini çağırarak iş parçacığı tanıtıcısını açıkça kapatmayın.

Win32 **ExitThread** API 'si gibi, **_endthreadex** iş parçacığı tanıtıcısını kapatmaz. Bu nedenle, **_beginthreadex** ve **_Endthreadex**kullandığınızda, Win32 **CloseHandle** API 'sini çağırarak iş parçacığı tanıtıcısını kapatmanız gerekir.

> [!NOTE]
> **_endthread** ve **_endthreadex** , C++ iş parçacığında bekleyen yok edicilerin çağrılmamasına neden oluyor.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_endthread**|\<Process. h >|
|**_endthreadex**|\<Process. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) çok iş parçacıklı sürümleri.

## <a name="example"></a>Örnek

[_Beginthread](beginthread-beginthreadex.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
