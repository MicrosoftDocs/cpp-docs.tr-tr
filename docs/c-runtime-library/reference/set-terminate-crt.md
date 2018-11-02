---
title: set_terminate (CRT)
ms.date: 11/04/2016
apiname:
- set_terminate
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
- set_terminate
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
ms.openlocfilehash: 7be81dec7fba80a273d635cbd30b96b09928bc66
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493918"
---
# <a name="setterminate-crt"></a>set_terminate (CRT)

Kendi sonlandırma yordamı çağrılacak yükler **sonlandırmak**.

## <a name="syntax"></a>Sözdizimi

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Parametreler

*termFunction*<br/>
Yazdığınız bir sonlandırma işlevi işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Tarafından kaydedilen önceki işlevine bir işaretçi döndürür **set_terminate** böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız dönüş değeri, varsayılan davranışı geri yüklemek için kullanılabilir; Bu değer olabilir **NULL**.

## <a name="remarks"></a>Açıklamalar

**Set_terminate** işlev yükler *termFunction* çağrılan işlev olarak **sonlandırmak**. **set_terminate** C++ özel durum işleme ile kullanılır ve özel durum önce programınızda herhangi bir noktada çağrılabilir. **sonlandırma** çağrıları [iptal](abort.md) varsayılan olarak. Kendi sonlandırma işlevi yazma ve arama bu varsayılanı değiştirebileceğiniz **set_terminate** bağımsız değişken olarak işlevinizi adı. **sonlandırma** bağımsız değişkeni olarak verilen son işlevi çağırır **set_terminate**. Temizleme görevleri gerçekleştirme herhangi istenen sonra *termFunction* programdan çıkmak. (Arayanına dönerse), mevcut değil ise, [iptal](abort.md) çağrılır.

Çok iş parçacıklı bir ortamda, sonlandırma işlevleri her bir iş parçacığı için ayrı olarak korunur. Her yeni bir iş parçacığı kendi sonlandırma işlevi yüklemeniz gerekir. Bu nedenle, her iş parçacığının kendi sonlandırma işlemeyi sorumlu olduğu.

**Terminate_function** türü EH içinde tanımlanmıştır. Bir kullanıcı tanımlı sonlandırma işlevi işaretçisi olarak H *termFunction* döndüren **void**. Özel işlevinizi *termFunction* hiçbir bağımsız değişken alabilir ve arayanına döndürmemelidir. Aksi halde [iptal](abort.md) çağrılır. Bir özel durum içinden oluşturulabilir değil *termFunction*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate** işlevi yalnızca hata ayıklayıcı dışında çalışır.

Tek bir yoktur **set_terminate** işleyicisi için tüm dinamik olarak bağlı dll veya exe; çağırsanız bile **set_terminate** işleyicinizi bir başkası tarafından değiştirilebilir veya bir başkası tarafından ayarlanmış bir işleyici değiştirme DLL veya EXE.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**set_terminate**|\<EH.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [sonlandırmak](terminate-crt.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
