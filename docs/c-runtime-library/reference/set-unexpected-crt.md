---
description: 'Hakkında daha fazla bilgi edinin: set_unexpected (CRT)'
title: set_unexpected (CRT)
ms.date: 1/14/2021
api_name:
- set_unexpected
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- set_unexpected
helpviewer_keywords:
- set_unexpected function
- unexpected function
- exception handling, termination
ms.assetid: ebcef032-4771-48e5-88aa-2a1ab8750aa6
ms.openlocfilehash: b9918e152a5d27c853aef7769b932ee4efedeef8
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242637"
---
# <a name="set_unexpected-crt"></a>`set_unexpected` CRT

Tarafından çağrılacak kendi sonlandırma işlevinizi kurar **`unexpected`** .

## <a name="syntax"></a>Sözdizimi

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Parametreler

*`unexpFunction`*\
İşlevi değiştirmek için yazdığınız bir işlevin işaretçisi **`unexpected`** .

## <a name="return-value"></a>Dönüş Değeri

**`_set_unexpected`** Önceki işlevin daha sonra geri yüklenebilmesi için tarafından kaydedilen önceki sonlandırma işlevine yönelik bir işaretçi döndürür. Önceki bir işlev ayarlanmamışsa, varsayılan davranışı geri yüklemek için dönüş değeri kullanılabilir; Bu değer olabilir **`NULL`** .

## <a name="remarks"></a>Açıklamalar

**`set_unexpected`** İşlevi, tarafından çağrılan işlev olarak *unexpFunction* 'yi yüklüyor **`unexpected`** . **`unexpected`** Geçerli C++ özel durum işleme uygulamasında kullanılmaz. **`unexpected_function`** Tür Eh içinde tanımlanır. Kullanıcı tanımlı beklenmeyen bir işlevin işaretçisi olarak H, döndüren *unexpFunction* **`void`** . Özel *unexpFunction* işleviniz çağırana dönmemelidir.

```cpp
typedef void ( *unexpected_function )( );
```

Varsayılan olarak, **`unexpected`** çağırır **`terminate`** . Kendi sonlandırma işlevinizi yazarak ve **`set_unexpected`** bağımsız değişkeni olarak işlevinizin adıyla çağırarak, bu varsayılan davranışı değiştirebilirsiniz. **`unexpected`** bağımsız değişken olarak verilen son işlevi çağırır **`set_unexpected`** .

Bir çağrısı tarafından yüklenen özel sonlandırma işlevinin aksine **`set_terminate`** , içinden bir özel durum oluşturulabilir **`unexpFunction`** .

Çok iş parçacıklı bir ortamda, her iş parçacığı için beklenmeyen işlevler ayrı olarak korunur. Her yeni iş parçacığının kendi beklenmeyen işlevini yüklemesi gerekir. Bu nedenle, her iş parçacığı kendi beklenmeyen işleme üzerinden ücretlendirilir.

C++ özel durum işlemenin geçerli Microsoft uygulamasında, **`unexpected`** **`terminate`** Varsayılan olarak çağırır ve özel durum işleme çalışma zamanı kitaplığı tarafından hiçbir zaman çağrılmaz. **`unexpected`** **TERMINATE** yerine çağırmanın belirli bir avantajı yoktur.

**`set_unexpected`** Dinamik olarak bağlı tüm dll 'ler veya EXEs 'ler için tek bir işleyici vardır; işleyicinizi çağırsanız bile **`set_unexpected`** başka bir dll veya exe tarafından ayarlanmış bir işleyiciyi değiştirseniz bile.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**`set_unexpected`**|`<eh.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum Işleme yordamları](../../c-runtime-library/exception-handling-routines.md)\
[`abort`](abort.md)\
[`_get_unexpected`](get-unexpected.md)\
[`set_terminate`](set-terminate-crt.md)\
[`terminate`](terminate-crt.md)\
[`unexpected`](unexpected-crt.md)\
