---
title: set_unexpected (CRT)
ms.date: 11/04/2016
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
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: 6c38421e447ca7b3f263148f51f0ade5c59e2804
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484233"
---
# <a name="setunexpected-crt"></a>set_unexpected (CRT)

Kendi sonlandırma işlevi çağrılacak yükler **beklenmeyen**.

## <a name="syntax"></a>Sözdizimi

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Parametreler

*unexpFunction*<br/>
Değiştirilecek yazan bir işlev işaretçisi **beklenmeyen** işlevi.

## <a name="return-value"></a>Dönüş Değeri

Önceki sonlandırma işlevi işaretçisi kayıtlı tarafından döndürür **_set_unexpected** böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız dönüş değeri, varsayılan davranışı geri yüklemek için kullanılabilir; Bu değer olabilir **NULL**.

## <a name="remarks"></a>Açıklamalar

**Set_unexpected** işlev yükler *unexpFunction* çağrılan işlev olarak **beklenmeyen**. **Beklenmeyen** geçerli C++ özel durum işleme uygulamada kullanılmaz. **Unexpected_function** türü EH içinde tanımlanmıştır. Bir kullanıcı tanımlı beklenmeyen işlev işaretçisi olarak H *unexpFunction* döndüren **void**. Kendi özel *unexpFunction* işlevi arayanına döndürmemelidir.

```cpp
typedef void ( *unexpected_function )( );
```

Varsayılan olarak, **beklenmeyen** çağrıları **sonlandırmak**. Kendi sonlandırma işlevi yazma ve arama bu varsayılan davranışı değiştirebilirsiniz **set_unexpected** bağımsız değişken olarak işlevinizi adı. **Beklenmeyen** bağımsız değişkeni olarak verilen son işlevi çağırır **set_unexpected**.

Farklı bir çağrı tarafından yüklenen özel sonlandırma işlevi **set_terminate**, içinden bir özel durum *unexpFunction*.

Çok iş parçacıklı bir ortamda, beklenmeyen işlevleri her bir iş parçacığı için ayrı olarak korunur. Her yeni bir iş parçacığı beklenmeyen kendi işlevine yüklemeniz gerekir. Bu nedenle, her iş parçacığının kendi beklenmeyen işleme sorumlu olduğu.

C++ özel durum işleme, geçerli Microsoft uygulamasındaki **beklenmeyen** çağrıları **sonlandırmak** varsayılan ve özel durum işleme çalışma zamanı kitaplığı tarafından hiçbir zaman çağrılır. Arama için belirli bir avantajı yoktur **beklenmeyen** yerine **sonlandırmak**.

Tek bir yoktur **set_unexpected** işleyicisi için tüm dinamik olarak bağlı dll veya exe; çağırsanız bile **set_unexpected** işleyicinizi bir başkası tarafından değiştirilebilir veya belirlediği bir işleyici değiştirmediğiniz başka bir DLL veya EXE.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**set_unexpected**|\<EH.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
