---
title: errno, _doserrno, _sys_errlist, and _sys_nerr
ms.date: 11/04/2016
api_name:
- _errno
api_location:
- msvcrt.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _sys_errlist
- errno
- _sys_nerr
- _doserrno
helpviewer_keywords:
- error codes, printing
- sys_errlist global variable
- doserrno global variable
- errno global variable
- _doserrno global variable
- _sys_errlist global variable
- _sys_nerr global variable
- sys_nerr global variable
ms.assetid: adbec641-6d91-4e19-8398-9a34046bd369
ms.openlocfilehash: 5b10d98dab41151290d4e44e031f659108b0c73c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944563"
---
# <a name="errno-_doserrno-_sys_errlist-and-_sys_nerr"></a>errno, _doserrno, _sys_errlist, and _sys_nerr

Program yürütmesi sırasında ayarlanan hata kodlarını tutan ve görüntüleme için hata kodlarının dize eşdeğerleri olan genel makrolar.

## <a name="syntax"></a>Sözdizimi

```
#define errno   (*_errno())
#define _doserrno   (*__doserrno())
#define _sys_errlist (__sys_errlist())
#define _sys_nerr (*__sys_nerr())
```

## <a name="remarks"></a>Açıklamalar

Her ikisi de `errno` program başlatma sırasında çalışma zamanı tarafından 0 olarak ayarlanır. `_doserrno` `errno`sistem düzeyindeki bir çağrıda bir hata üzerinde ayarlanır. , Tarafından ayarlanan son çağrının değerini taşıdığıiçin,budeğerbaşarılıçağrılartarafındandeğiştirilebilir.`errno` Hata üzerinde ayarlanan `errno` çalışma zamanı kitaplık çağrıları başarılı bir şekilde temizlemez `errno` . Kendisini ayarlayabilmesi için `_set_errno(0)` hemen önce çağırarak her zaman temizleyin `errno` ve çağrıdan hemen sonra kontrol edin.

Bir hata durumunda, `errno` bir sistem çağrısı tarafından döndürülen hata koduyla aynı değere ayarlı değildir. G/ç işlemleri için, `_doserrno` `errno` kodların işletim sistemi hata kodu eşdeğerlerini depolar. G/ç dışı işlemler için, değeri `_doserrno` ayarlı değildir.

Her `errno` değer, ' deki `_sys_errlist` bir hata iletisiyle ilişkilendirilir ve bu, [pError](../c-runtime-library/reference/perror-wperror.md) işlevlerinden biri kullanılarak yazdırılabilir veya [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) veya [strerror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) işlevlerinden biri kullanılarak bir dizeye depolanır. `_sys_errlist` `_sys_nerr`Ve işlevleri, hata bilgilerini `_sys_errlist` işlemek için diziyi ve — içindeki öğe sayısı ' nı kullanır. `strerror` `perror` `_sys_errlist` Ve '`_sys_nerr` a doğrudan erişim, kod güvenliği nedenleriyle kullanım dışıdır. Burada gösterildiği gibi, genel makrolar yerine daha güvenli, işlevsel sürümleri kullanmanızı öneririz:

|Genel makro|İşlevsel Eşdeğerleri|
|------------------|----------------------------|
|`_doserrno`|[_get_doserrno](../c-runtime-library/reference/get-doserrno.md), [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)|
|`errno`|[_get_errno](../c-runtime-library/reference/get-errno.md), [_set_errno](../c-runtime-library/reference/set-errno.md)|
|`_sys_errlist`, `_sys_nerr`|[strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|

Kitaplık matematik yordamları `errno` [_matherr](../c-runtime-library/reference/matherr.md)çağırarak ayarlanır. Matematik hatalarını farklı şekilde işlemek için, `_matherr` başvuru açıklamasına göre kendi yordamını yazın ve `_matherr`adlandırın.

Aşağıdaki `errno` tablodaki tüm değerler errno. h > içindeki \<önceden tanımlanmış sabitlerdir ve UNIX ile uyumludur. Yalnızca `ERANGE`, `EILSEQ`, ve`EDOM` ISO C99 standardında belirtilir.

|Sabit|Sistem hatası iletisi|Değer|
|--------------|--------------------------|-----------|
|`EPERM`|İşleme izin verilmiyor|1\.|
|`ENOENT`|Böyle bir dosya ya da dizin yok|2|
|`ESRCH`|Böyle bir işlem yok|3|
|`EINTR`|Kesintiye uğramış işlev|4|
|`EIO`|G/Ç hatası|5|
|`ENXIO`|Böyle bir cihaz veya adres yok|6|
|`E2BIG`|Bağımsız değişken listesi çok uzun|7|
|`ENOEXEC`|Exec biçim hatası|8|
|`EBADF`|Hatalı dosya numarası|9|
|`ECHILD`|Üretilmiş işlem yok|10|
|`EAGAIN`|Daha fazla işlem yok veya bellek yetersiz ya da en fazla iç içe geçme düzeyine ulaşılmış|11|
|`ENOMEM`|Yeterli bellek yok|12|
|`EACCES`|İzin reddedildi|13|
|`EFAULT`|Hatalı adres|14|
|`EBUSY`|Cihaz veya kaynak meşgul|16|
|`EEXIST`|Dosya mevcut|17|
|`EXDEV`|Çapraz cihaz bağlantısı|18|
|`ENODEV`|Böyle bir cihaz yok|19|
|`ENOTDIR`|Bir dizin değil|20|
|`EISDIR`|Bir dizin|21|
|`EINVAL`|Geçersiz bağımsız değişken|22|
|`ENFILE`|Sistemde çok fazla dosya açık|23|
|`EMFILE`|Çok fazla dosya açık|24|
|`ENOTTY`|Uygun olmayan G/Ç denetimi işlemi|25|
|`EFBIG`|Dosya çok büyük|27|
|`ENOSPC`|Cihazda alan kalmadı|28|
|`ESPIPE`|Geçersiz arama|29|
|`EROFS`|Salt okunur dosya sistemi|30|
|`EMLINK`|Çok fazla bağlantı|31|
|`EPIPE`|Kesik kanal|32|
|`EDOM`|Matematik bağımsız değişkeni|33|
|`ERANGE`|Sonuç çok büyük|34|
|`EDEADLK`|Kaynak kilitlenmesi oluşabilir|36|
|`EDEADLOCK`|Önceki Microsoft C sürümleriyle uyumluluk için EDEADLK aynı|36|
|`ENAMETOOLONG`|Dosya adı çok uzun|38|
|`ENOLCK`|Kullanılabilir kilit yok|39|
|`ENOSYS`|İşlev desteklenmiyor|40|
|`ENOTEMPTY`|Dizin boş değil|41|
|`EILSEQ`|Geçersiz bayt dizisi|42|
|`STRUNCATE`|Dize kesildi|80|

## <a name="requirements"></a>Gereksinimler

|Genel makro|Gerekli başlık|İsteğe bağlı başlık|
|------------------|---------------------|---------------------|
|`errno`|\<errno. h > veya \<Stdlib. h >, \<cerrno > veya \<cstdlib > (C++)||
|`_doserrno`, `_sys_errlist`, `_sys_nerr`|\<Stdlib. h >, \<cstdlib > (C++)|\<errno. h >, \<cerrno > (C++)|

`_doserrno`, Vemakroları`_sys_nerr`Microsoftuzantılarıdır. `_sys_errlist` Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Global Değişkenler](../c-runtime-library/global-variables.md)<br/>
[errno sabitleri](../c-runtime-library/errno-constants.md)<br/>
[perror, _wperror](../c-runtime-library/reference/perror-wperror.md)<br/>
[strerror, _strerror, _wcserror, \__wcserror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)<br/>
[strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)<br/>
[_get_doserrno](../c-runtime-library/reference/get-doserrno.md)<br/>
[_set_doserrno](../c-runtime-library/reference/set-doserrno.md)<br/>
[_get_errno](../c-runtime-library/reference/get-errno.md)<br/>
[_set_errno](../c-runtime-library/reference/set-errno.md)
