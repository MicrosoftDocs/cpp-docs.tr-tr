---
title: set_unexpected (CRT)
ms.date: 11/04/2016
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
ms.openlocfilehash: f05eab14a53c8abc119a8014d5ac99dc076a9c25
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226170"
---
# <a name="set_unexpected-crt"></a>set_unexpected (CRT)

**Beklenmeyen**bir şekilde çağrılacak kendi sonlandırma işlevinizi kurar.

## <a name="syntax"></a>Söz dizimi

```cpp
unexpected_function set_unexpected( unexpected_function unexpFunction );
```

### <a name="parameters"></a>Parametreler

*unexpFunction*<br/>
**Beklenmeyen** işlevi değiştirmek için yazdığınız bir işleve yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Önceki işlevin daha sonra geri yüklenebilmesi için **_set_unexpected** tarafından kaydedilen önceki sonlandırma işlevine yönelik bir işaretçi döndürür. Önceki bir işlev ayarlanmamışsa, varsayılan davranışı geri yüklemek için dönüş değeri kullanılabilir; Bu değer **null**olabilir.

## <a name="remarks"></a>Açıklamalar

**Set_unexpected** işlevi, **beklenmeyen**bir şekilde çağrılan Işlev olarak *unexpFunction* 'yi yüklüyor. Geçerli C++ özel durum işleme uygulamasında **beklenmeyen** bir şekilde kullanılmıyor. **Unexpected_function** türü Eh içinde tanımlanır. Kullanıcı tanımlı beklenmeyen bir işlevin işaretçisi olarak H, döndüren *unexpFunction* **`void`** . Özel *unexpFunction* işleviniz çağırana dönmemelidir.

```cpp
typedef void ( *unexpected_function )( );
```

Varsayılan olarak, **beklenmeyen** çağrılar **sonlandırılır**. Kendi sonlandırma işlevinizi yazarak ve bağımsız değişkeni olarak işlevinizin adını **set_unexpected** çağırarak, bu varsayılan davranışı değiştirebilirsiniz. **beklenmeyen** bir bağımsız değişken olarak verilen son işlevi çağıran **set_unexpected**.

Bir **set_terminate**çağrısıyla yüklenen özel sonlandırma işlevinin aksine, *unexpFunction*içinden bir özel durum oluşturulabilir.

Çok iş parçacıklı bir ortamda, her iş parçacığı için beklenmeyen işlevler ayrı olarak korunur. Her yeni iş parçacığının kendi beklenmeyen işlevini yüklemesi gerekir. Bu nedenle, her iş parçacığı kendi beklenmeyen işleme üzerinden ücretlendirilir.

C++ özel durum işlemenin geçerli Microsoft uygulamasında, **beklenmeyen** çağrılar varsayılan olarak **sonlandırılır** ve özel durum işleme çalışma zamanı kitaplığı tarafından hiçbir zaman çağrılmaz. **Terminate**yerine **beklenmeyen** bir şekilde çağırmanın belirli bir avantajı yoktur.

Dinamik olarak bağlı tüm dll 'Ler veya EXEs için tek bir **set_unexpected** işleyicisi vardır. **set_unexpected** çağırsanız bile işleyiciniz başka bir dll veya exe tarafından ayarlanmış bir işleyiciyi değiştirmiş olabilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**set_unexpected**|\<eh.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel durum Işleme yordamları](../../c-runtime-library/exception-handling-routines.md)<br/>
[durdur](abort.md)<br/>
[_get_unexpected](get-unexpected.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
[bek](unexpected-crt.md)<br/>
