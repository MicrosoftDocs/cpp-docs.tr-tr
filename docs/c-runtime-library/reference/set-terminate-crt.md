---
title: set_terminate (CRT) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_terminate function
- terminate function
- exception handling, termination
ms.assetid: 3ff1456a-7898-44bc-9266-a328a80b6006
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 017ea9d96cef9065ff82e7f3428e725b816c9319
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="setterminate-crt"></a>set_terminate (CRT)

Kendi sonlandırma yordamı çağrılacak yükler **sonlandırmak**.

## <a name="syntax"></a>Sözdizimi

```cpp
terminate_function set_terminate( terminate_function termFunction );
```

### <a name="parameters"></a>Parametreler

*termFunction*<br/>
Yazdığınız Sonlandır işlev işaretçisi.

## <a name="return-value"></a>Dönüş Değeri

Tarafından kaydedilen önceki işlevi için bir işaretçi döndüren **set_terminate** böylece önceki işlevi daha sonra geri yüklenebilir. Önceki bir işlev ayarlarsanız varsayılan davranışı geri dönüş değeri kullanılabilir; Bu değer NULL olabilir.

## <a name="remarks"></a>Açıklamalar

**Set_terminate** işlev yükler *termFunction* çağrılan işlev olarak **sonlandırmak**. **set_terminate** ile C++ özel durum işleme kullanılır ve özel durum önce programınızdaki herhangi bir noktada çağrılabilir. **sonlandırma** çağrıları [abort](abort.md) varsayılan olarak. Kendi sonlandırma işlevi yazma ve arama bu varsayılan ayarı değiştirebilirsiniz **set_terminate** işlevinizi bağımsız değişkeni olarak adı. **sonlandırma** bağımsız değişken olarak verilen son işlevi çağırır **set_terminate**. Temizleme görevleri herhangi gerçekleştirme istenen sonra *termFunction* program çıkmalıdır. (Çağırıcısına döndürürse), mevcut değilse, [abort](abort.md) olarak adlandırılır.

Birden çok iş parçacıklı bir ortamda, sonlandırma işlevleri her iş parçacığı için ayrı olarak korunur. Her yeni bir iş parçacığı kendi Sonlandır işlevi yüklemeniz gerekir. Bu nedenle, her iş parçacığının kendi sonlandırma işleme sorumlu olduğu.

**Terminate_function** türü EH içinde tanımlanmıştır. Bir sonlandırma kullanıcı tanımlı işlev işaretçisi olarak H *termFunction* döndüren **void**. Özel işlevinizi *termFunction* bağımsız değişkenler almayan ve çağırıcısına vermemelidir. Aşması durumunda [abort](abort.md) olarak adlandırılır. Bir özel durum içinden durum oluşturulabilir değil *termFunction*.

```cpp
typedef void ( *terminate_function )( );
```

> [!NOTE]
> **Set_terminate** işlevi yalnızca hata ayıklayıcı dışında çalışır.

Tek bir yoktur **set_terminate** işleyicisi tüm dinamik olarak bağlı dll veya exe; bile çağırırsanız **set_terminate** işleyiciniz başka tarafından değiştirilebilir veya bir başkası tarafından ayarlanmış bir işleyici değiştirme DLL veya EXE.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**set_terminate**|\<EH.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [sonlandırmak](terminate-crt.md).

## <a name="see-also"></a>Ayrıca bkz.

[Özel Durum İşleme Rutinleri](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_get_terminate](get-terminate.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Sonlandırma](terminate-crt.md)<br/>
[beklenmeyen](unexpected-crt.md)<br/>
