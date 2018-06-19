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
ms.openlocfilehash: d4588829b3ec1d348405be925a75c493f4e8594b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397759"
---
# <a name="endthread-endthreadex"></a>_endthread, _endthreadex

Bir iş parçacığını sonlandırır; **_endthread** tarafından oluşturulan bir iş parçacığını sonlandırır **_beginthread** ve **_endthreadex** tarafından oluşturulan bir iş parçacığını sonlandırır **_beginthreadex**.

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

Çağırabilirsiniz **_endthread** veya **_endthreadex** açıkça bir iş parçacığı; sonlandırmak için ancak **_endthread** veya **_endthreadex** çağrılır iş parçacığı yordamından döndüğünde otomatik olarak geçirilen parametre olarak **_beginthread** veya **_beginthreadex**. Bir iş parçacığı çağrısıyla sonlandırma **endthread** veya **_endthreadex** iş parçacığı için ayrılan kaynakların doğru kurtarma sağlamaya yardımcı olur.

> [!NOTE]
> Libcmt.lib ile bağlantılı bir yürütülebilir dosya için Win32 çağırmayın [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API; Bu, ayrılan kaynakları geri kazanma çalışma zamanı sistem engeller. **_endthread** ve **_endthreadex** ayrılmış iş parçacığı kaynaklarını geri kazanmak ve ardından arama **ExitThread**.

**_endthread** iş parçacığı tutamacı otomatik olarak kapanır. (Bu davranış Win32 farklıdır **ExitThread** API.) Bu nedenle, kullandığınızda **_beginthread** ve **_endthread**, açıkça iş parçacığı tutamacı Win32 çağırarak kapatmayın [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API.

Win32 gibi **ExitThread** API, **_endthreadex** iş parçacığı tutamacı kapatmaz. Bu nedenle, kullandığınızda **_beginthreadex** ve **_endthreadex**, Win32 çağırarak iş parçacığı tutamacı kapatmalısınız **CloseHandle** API.

> [!NOTE]
> **_endthread** ve **_endthreadex** C++ Yıkıcılar bekleyen değil çağrılacak parçacığında neden.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_endthread**|\<Process.h >|
|**_endthreadex**|\<Process.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Birden çok iş parçacıklı sürümlerini [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Örneğin bkz [_beginthread](beginthread-beginthreadex.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
