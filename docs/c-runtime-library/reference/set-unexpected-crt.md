---
title: set_unexpected (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- set_unexpected
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
- set_unexpected
dev_langs:
- C++
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c740f74dc13ea22819d0f792bfc1e3dbcc9f425e
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

Çağrılacak kendi sonlandırma işlev yükler **beklenmeyen**.

## <a name="syntax"></a>Sözdizimi

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Parametreler

*unexpFunction*<br/>
Değiştirmek için yazma bir işlev işaretçisi **beklenmeyen** işlevi.

## <a name="return-value"></a>Dönüş Değeri

Önceki sonlandırma işlevi için bir işaretçi kayıtlı tarafından döndürür **_set_unexpected** böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız varsayılan davranışı geri dönüş değeri kullanılabilir; Bu değer NULL olabilir.

## <a name="remarks"></a>Açıklamalar

**Set_unexpected** işlev yükler *unexpFunction* çağrılan işlev olarak **beklenmeyen**. **Beklenmeyen** geçerli C++ özel durum işleme uygulamasında kullanılmaz. **Unexpected_function** türü EH içinde tanımlanmıştır. Bir kullanıcı tanımlı beklenmeyen işlev işaretçisi olarak H *unexpFunction* döndüren **void**. Özel *unexpFunction* işlevi çağırıcısına döndürmemelidir.

```cpp
typedef void ( *unexpected_function )( );
```

Varsayılan olarak, **beklenmeyen** çağrıları **sonlandırmak**. Kendi sonlandırma işlevi yazma ve arama bu varsayılan davranışı değiştirebilirsiniz **set_unexpected** işlevinizi bağımsız değişkeni olarak adı. **Beklenmeyen** bağımsız değişken olarak verilen son işlevi çağırır **set_unexpected**.

Bir çağrı tarafından yüklenen özel sonlandırma işlevi aksine **set_terminate**, bir özel durum içinden atılabilen *unexpFunction*.

Birden çok iş parçacıklı bir ortamda, beklenmeyen işlevleri her iş parçacığı için ayrı ayrı tutulur. Her yeni bir iş parçacığı beklenmeyen işlevini yüklemesi gerekir. Bu nedenle, her iş parçacığı beklenmeyen kendi işleme sorumlu olur.

C++ özel durum işleme, geçerli Microsoft uygulamasındaki **beklenmeyen** çağrıları **sonlandırmak** varsayılan ve özel durum işleme çalışma zamanı kitaplığı tarafından hiçbir zaman çağrılır. Arama için belirli bir avantajı vardır **beklenmeyen** yerine **sonlandırmak**.

Tek bir yoktur **set_unexpected** işleyicisi tüm dinamik olarak bağlı dll veya exe; bile çağırırsanız **set_unexpected** işleyiciniz başka tarafından değiştirilebilir veya tarafından belirlenen bir işleyici değiştirme başka bir DLL veya EXE.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**set_unexpected**|\<EH.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[Sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
