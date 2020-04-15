---
title: _getdcwd, _wgetdcwd
ms.date: 4/2/2020
api_name:
- _getdcwd
- _wgetdcwd
- _o__getdcwd
- _o__wgetdcwd
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
ms.openlocfilehash: 3a4ca8ff3f1153893282c65bc4c2becd687138ce
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81344394"
---
# <a name="_getdcwd-_wgetdcwd"></a>_getdcwd, _wgetdcwd

Belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu alır.

## <a name="syntax"></a>Sözdizimi

```C
char *_getdcwd(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Parametreler

*Sürücü*<br/>
Sürücüyü belirten negatif olmayan bir tamsayı (0 = varsayılan sürücü, 1 = A, 2 = B vb.).

Belirtilen sürücü kullanılamıyorsa veya sürücü türü (örneğin, çıkarılabilir, sabit, CD-ROM, RAM disk veya ağ sürücüsü) belirlenemezse, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için [Parametre Doğrulama'ya](../../c-runtime-library/parameter-validation.md)bakın.

*Arabellek*<br/>
Yol için depolama konumu veya **NULL**.

**NULL** belirtilirse, bu işlev **malloc**kullanarak en az *maxlen* boyutunda bir arabellek ayırır ve **_getdcwd'nin** geri dönüş değeri ayrılan arabelleğe işaretçidir. Arabellek **özgür** çağırArak ve işaretçi geçirerek serbest bırakılabilir.

*makslen*<br/>
Karakterlerde yolun maksimum uzunluğunu belirten sıfır olmayan pozitif tamsayı: **_getdcwd** için **char** ve **_wgetdcwd**için **wchar_t.**

*Maxlen* sıfırdan küçük veya eşitse, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için [Parametre Doğrulama'ya](../../c-runtime-library/parameter-validation.md)bakın.

## <a name="return-value"></a>Dönüş Değeri

Belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu temsil eden bir dize işaretçisi veya bir hatayı gösteren **NULL.**

*Arabellek* **NULL** olarak belirtilirse ve *maxlen* karakterleri ayırmak için yeterli bellek varsa, bir hata oluşur ve **errno** **ENOMEM**olarak ayarlanır. Sonlandırıcı null karakteri de içeren yolun uzunluğu *maxlen*aşıyorsa, bir hata oluşur ve **errno** **ERANGE**olarak ayarlanır. Bu hata kodları hakkında daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

## <a name="remarks"></a>Açıklamalar

**_getdcwd** işlevi, belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu alır ve *arabellekte*depolar. Geçerli çalışma dizini köke ayarlanmışsa, dize bir\\ters eğik çizgi ile sona erer ( . Geçerli çalışma dizini kök dışında bir dizin olarak ayarlanmışsa, dize bir ters eğik çizgi ile değil, dizin adı ile sona erer.

**_wgetdcwd** **_getdcwd**geniş karakterli bir sürümüdür ve *arabellek* parametresi ve dönüş değeri geniş karakterli dizeleridir. Aksi takdirde, **_wgetdcwd** ve **_getdcwd** aynı şekilde çalışır.

Bu işlev, iş parçacığı güvenli olmayan **GetFullPathName'e**bağlı olsa da iş parçacığı için güvenlidir. Ancak, çok iş parçacığı uygulamanız hem bu işlevi hem de [GetFullPathName'i](/windows/win32/api/fileapi/nf-fileapi-getfullpathnamew)çağırırsa iş parçacığı güvenliğini ihlal edebilirsiniz.

Bu işlevin **_nolock** soneki olan sürümü, iş parçacığı güvenli olmaması ve diğer iş parçacıkları tarafından girişimden korunmaması dışında bu işlek aynı şekilde çalışır. Daha fazla bilgi için [_getdcwd_nolock _wgetdcwd_nolock.](getdcwd-nolock-wgetdcwd-nolock.md)

**_DEBUG** ve **_CRTDBG_MAP_ALLOC** tanımlandığında, bellek ayırmalarını hata ayıklamanız için **_getdcwd** ve **_wgetdcwd** çağrıları **_getdcwd_dbg** ve **_wgetdcwd_dbg** yapılan çağrılarla değiştirilir. Daha fazla bilgi için[_getdcwd_dbg _wgetdcwd_dbg.](getdcwd-dbg-wgetdcwd-dbg.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdcwd**|\<direct.h>|
|**_wgetdcwd**|\<direct.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_getdrive'daki](getdrive.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Kontrolü](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
