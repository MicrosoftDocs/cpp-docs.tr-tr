---
title: errno, _doserrno, _sys_errlist, and _sys_nerr
ms.date: 11/04/2016
apiname:
- _errno
apilocation:
- msvcrt.dll
apitype: DLLExport
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
ms.openlocfilehash: 57d04fe5867c6a969b6aeca40f26b18b5dcd7a61
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62344050"
---
# <a name="errno-doserrno-syserrlist-and-sysnerr"></a>errno, _doserrno, _sys_errlist, and _sys_nerr

Bu hata kodlarını tutan genel makrolar, program yürütme ve hata kodlarını görüntülemek için dize eşdeğerleri sırasında ayarlanır.

## <a name="syntax"></a>Sözdizimi

```
#define errno   (*_errno())
#define _doserrno   (*__doserrno())
#define _sys_errlist (__sys_errlist())
#define _sys_nerr (*__sys_nerr())
```

## <a name="remarks"></a>Açıklamalar

Her ikisi de `errno` ve `_doserrno` 0 olarak program açılışında çalışma zamanı tarafından ayarlanır. `errno` sistem düzeyinde çağrıda bir hatada ayarlanır. Çünkü `errno` tutar, bu değeri ayarlayan son çağrının değerini takip eden çağrılar tarafından değiştirilebilir. Çalışma Zamanı Kitaplığı `errno` bir hatada silmeyin `errno` başarılı. Her zaman Temizle `errno` çağırarak `_set_errno(0)` hemen ayarlayın ve ve çağrının ardından hemen denetleyin bir çağrıdan önce.

Bir hatada `errno` mutlaka aynı değere bir sistem çağrısı tarafından döndürülen hata kodu olarak ayarlanmadı. G/ç işlemleri `_doserrno` işletim sistemi hata kodu eşdeğerleri depolar `errno` kodları. Çoğu olmayan g/Ç işlemleri için değerini `_doserrno` ayarlı değil.

Her `errno` değeri, bir hata iletisi ile ilişkilendirilmiş `_sys_errlist` , yazdırılabilir birini kullanarak [perror](../c-runtime-library/reference/perror-wperror.md) işlevleri veya birini kullanarak bir dizede depolanan [strerror](../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md) veya [strerror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md) işlevleri. `perror` Ve `strerror` işlevleri kullanmak `_sys_errlist` dizi ve `_sys_nerr`— içindeki öğelerin sayısını `_sys_errlist`— hata bilgilerini işlemek için. Doğrudan erişim `_sys_errlist` ve `_sys_nerr` kod güvenlik nedenleriyle kullanım dışı bırakılmıştır. Genel makrolar yerine daha güvenli ve işlevsel sürümleri kullanmanız burada gösterildiği gibi öneririz:

|Genel makrosu|İşlevsel Eşdeğerleri|
|------------------|----------------------------|
|`_doserrno`|[_get_doserrno](../c-runtime-library/reference/get-doserrno.md), [_set_doserrno](../c-runtime-library/reference/set-doserrno.md)|
|`errno`|[_get_errno](../c-runtime-library/reference/get-errno.md), [_set_errno](../c-runtime-library/reference/set-errno.md)|
|`_sys_errlist`, `_sys_nerr`|[strerror_s, _strerror_s, _wcserror_s, \__wcserror_s](../c-runtime-library/reference/strerror-s-strerror-s-wcserror-s-wcserror-s.md)|

Kitaplık matematik yordamları kümesi `errno` çağırarak [_matherr](../c-runtime-library/reference/matherr.md). Matematik hatalarını farklı şekilde işlemek için kendi yordamınızı göre yazma `_matherr` başvurusunun açıklamasına ve adlandırın `_matherr`.

Tüm `errno` değerler aşağıdaki tabloda önceden tanımlanmış sabitleri de \<errno.h >, ve UNIX uyumludur. Yalnızca `ERANGE`, `EILSEQ`, ve `EDOM` ISO C99 standardında belirtilmiştir.

|Sabit|Sistem hatası iletisi|Değer|
|--------------|--------------------------|-----------|
|`EPERM`|İşleme izin verilmiyor|1.|
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

|Genel makrosu|Gerekli başlık|İsteğe bağlı başlık|
|------------------|---------------------|---------------------|
|`errno`|\<errno.h > veya \<stdlib.h >, \<cerrno > veya \<cstdlib > (C++)||
|`_doserrno`, `_sys_errlist`, `_sys_nerr`|\<stdlib.h>, \<cstdlib> (C++)|\<errno.h>, \<cerrno> (C++)|

`_doserrno`, `_sys_errlist`, Ve `_sys_nerr` Microsoft uzantıları makrolardır. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../c-runtime-library/compatibility.md).

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
