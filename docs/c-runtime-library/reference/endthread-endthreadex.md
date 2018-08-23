---
title: _endthread, _endthreadex | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _endthread
- _endthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _endthread
- endthreadex
- _endthreadex
- endthread
dev_langs:
- C++
helpviewer_keywords:
- _endthread function
- endthread function
- terminating threads
- endthreadex function
- _endthreadex function
- threading [C++], terminating threads
ms.assetid: 18a91f2f-659e-40b4-b266-ec12dcf2abf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 898281e0652345f22c63076cf4b0a73294faaf04
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/16/2018
ms.locfileid: "42464991"
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex

Bir iş parçacığı sona erer; **_endthread** tarafından oluşturulan bir iş parçacığı sonlandırıldığında **_beginthread** ve **_endthreadex** tarafından oluşturulan bir iş parçacığı sonlandırıldığında **_beginthreadex**.

## <a name="syntax"></a>Sözdizimi

```C
void _endthread( void );
void _endthreadex(
   unsigned retval
);
```

### <a name="parameters"></a>Parametreler

*retval* iş parçacığı çıkış kodu.

## <a name="remarks"></a>Açıklamalar

Çağırabilirsiniz **_endthread** veya **_endthreadex** açıkça bir iş parçacığını sonlandırmak için ancak **_endthread** veya **_endthreadex** çağrılır iş parçacığı yordamdan döndüğünde otomatik olarak geçirilen bir parametre olarak **_beginthread** veya **_beginthreadex**. Çağrısıyla bir iş parçacığı sonlandırma **endthread** veya **_endthreadex** iş parçacığına ayrılan kaynakların doğru kurtarma sağlamaya yardımcı olur.

> [!NOTE]
> LIBCMT.lib ile bağlantılı bir yürütülebilir dosya için Win32 çağırmayın [ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread) API; Bu, ayrılan kaynakları tekrar kullanılabilir hale çalışma zamanı sistemi engeller. **_endthread** ve **_endthreadex** ayrılan iş parçacığı kaynaklarını geri kazanır ve sonra çağrı **ExitThread**.

**_endthread** iş parçacığı işleyicisini otomatik olarak kapanır. (Bu davranış, Win32 farklıdır **ExitThread** API.) Bu nedenle, kullandığınız zaman **_beginthread** ve **_endthread**, açıkça iş parçacığı işleyicisini Win32 çağırarak kapatmayın [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API.

Win32 gibi **ExitThread** API **_endthreadex** iş parçacığı işleyicisini kapatmaz. Bu nedenle, kullandığınız zaman **_beginthreadex** ve **_endthreadex**, iş parçacığı işleyicisini Win32 çağırarak kapatmalısınız **CloseHandle** API.

> [!NOTE]
> **_endthread** ve **_endthreadex** değil çağrılacak iş parçacığında C++ yıkıcıları bekleyen neden.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_endthread**|\<Process.h >|
|**_endthreadex**|\<Process.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Çoklu iş parçacığı sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örneğin bakın [_beginthread](beginthread-beginthreadex.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
