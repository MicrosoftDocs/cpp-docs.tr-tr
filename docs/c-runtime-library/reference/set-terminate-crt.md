---
title: set_terminate (CRT)
ms.date: 4/2/2020
api_name:
- set_terminate
- _o_set_terminate
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
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 08ea5bb8c446fadac6a7bcf7ca172c5d14546776
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332099"
---
# <a name="set_terminate-crt"></a>set_terminate (CRT)

**Sonlandırma**tarafından çağrılacak kendi sonlandırma yordamınızı yükler.

## <a name="syntax"></a>Sözdizimi

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Parametreler

*termFunction*<br/>
Yazdığınız sonlandırma işlevini işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Önceki işlevin daha sonra geri yüklenabilmesi için **set_terminate** tarafından kayıtlı önceki işleve bir işaretçi döndürür. Önceki işlev ayarlanmadıysa, iade değeri varsayılan davranışı geri yüklemek için kullanılabilir; bu değer **NULL**olabilir.

## <a name="remarks"></a>Açıklamalar

**set_terminate** işlevi **sonlandırma**tarafından çağrılan işlev olarak *termFunction* yükler. **set_terminate** C++ özel durum işleme ile kullanılır ve özel durum atılmadan önce programınızın herhangi bir noktasında çağrılabilir. çağrıları varsayılan olarak [iptal](abort.md) **eder.** Kendi sonlandırma işlevinizi yazarak ve işlevinizin adı ile **set_terminate** çağırarak bu varsayılanı değiştirebilirsiniz. **set_terminate** için bir argüman olarak **set_terminate**verilen son işlevi çağırır . İstenilen herhangi bir temizleme görevini yerine *getirince, termFunction* programdan çıkmalıdır. Çıkmazsa (arayana dönerse), [iptal](abort.md) denir.

Çok iş parçacığı lı bir ortamda, sonlandırma işlevleri her iş parçacığı için ayrı ayrı tutulur. Her yeni iş parçacığıkendi sonlandırma işlevini yüklemesi gerekir. Böylece, her iş parçacığı kendi sonlandırma işleme sorumludur.

**terminate_function** türü EH tanımlanır. H kullanıcı tanımlı sonlandırma işlevi için bir işaretçi olarak, **geçersiz**döndürür *termİş .* Özel işlev *teriminiz* hiçbir bağımsız değişken alabilir ve arayana geri dönmemelidir. Varsa, [iptal](abort.md) denir. Bir istisna *termFunction*içinde atılamaz.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **set_terminate** işlevi yalnızca hata ayıklamanın dışında çalışır.

Tüm dinamik olarak bağlı DL'ler veya EX'ler için tek bir **set_terminate** işleyicisi vardır; **set_terminate** arasanız bile işleyiciniz başka bir işleyici yle değiştirilebilir veya başka bir DLL veya EXE tarafından ayarlanmış bir işleyiciyi değiştirebilirsiniz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**set_terminate**|\<eh.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Sonlandırma](terminate-crt.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[Iptal](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Sonlandır](terminate-crt.md)<br/>
[Beklen -medik](unexpected-crt.md)<br/>
