---
title: set_terminate (CRT)
ms.date: 11/04/2016
api_name:
- set_terminate
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
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 860789a3f2fda5ef13cadffa2a00dba4fbd2090a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948366"
---
# <a name="set_terminate-crt"></a>set_terminate (CRT)

**Terminate**tarafından çağrılacak kendi sonlandırma yordamınıza sahip olun.

## <a name="syntax"></a>Sözdizimi

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Parametreler

*termFunction*<br/>
Yazdığınız sonlandırma işlevine yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Önceki işlevin daha sonra geri yüklenebilmesi için **set_terminate** tarafından kaydedilen önceki işleve yönelik bir işaretçi döndürür. Önceki bir işlev ayarlanmamışsa, varsayılan davranışı geri yüklemek için dönüş değeri kullanılabilir; Bu değer **null**olabilir.

## <a name="remarks"></a>Açıklamalar

**Set_terminate** işlevi, **Terminate**tarafından çağrılan işlev olarak *termFunction* 'ı yüklüyor. **set_terminate** C++ özel durum işlemeyle kullanılır ve özel durum oluşturulmadan önce programınızdaki herhangi bir noktada çağrılabilir. Varsayılan olarak [iptal](abort.md) çağrıları **Sonlandır** . Kendi sonlandırma işlevinizi yazarak ve bağımsız değişkeni olarak işlevinizin adını **set_terminate** çağırarak bu varsayılan değeri değiştirebilirsiniz. **Sonlandır** , **set_terminate**için bağımsız değişken olarak verilen son işlevi çağırır. İstenen temizleme görevlerini gerçekleştirdikten sonra, *termFunction* programdan çıkmalıdır. Çıkış yoksa (çağıranı döndürürse), [iptal](abort.md) çağırılır.

Çok iş parçacıklı bir ortamda, sonlandırma işlevleri her iş parçacığı için ayrı olarak korunur. Her yeni iş parçacığının kendi Terminate işlevini yüklemesi gerekir. Bu nedenle, her iş parçacığı kendi sonlandırma işlemenin ücretlendirilmiştir.

**Terminate_function** türü Eh içinde tanımlanır. Kullanıcı tanımlı sonlandırma işlevinin işaretçisi olarak H, **void**döndüren *termFunction* . Özel işleviniz *termFunction* , bağımsız değişken alabilir ve çağırana dönmemelidir. Varsa, [iptal](abort.md) çağırılır. *TermFunction*içinden bir özel durum oluşmayabilir.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate** işlevi yalnızca hata ayıklayıcı dışında çalışır.

Dinamik olarak bağlı tüm dll 'Ler veya EXEs için tek bir **set_terminate** işleyicisi vardır. **set_terminate** çağırsanız bile işleyiciniz başka bir veya başka bir dll ya da exe tarafından ayarlanmış bir işleyiciyi değiştirmiş olabilirsiniz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**set_terminate**|\<Eh. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Sonlandır](terminate-crt.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırmayı](terminate-crt.md)<br/>
[bek](unexpected-crt.md)<br/>
