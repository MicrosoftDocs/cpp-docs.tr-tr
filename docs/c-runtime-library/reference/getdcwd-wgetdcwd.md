---
title: _getdcwd, _wgetdcwd
ms.date: 11/04/2016
api_name:
- _getdcwd
- _wgetdcwd
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
ms.openlocfilehash: 3b67e04e914baf85545fcde63cf27c86bc15fac1
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956021"
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

*sürücü*<br/>
Sürücüyü belirten negatif olmayan bir tamsayı (0 = varsayılan sürücü, 1 = A, 2 = B vb.).

Belirtilen sürücü kullanılamıyorsa veya sürücü türü (örneğin, çıkarılabilir, sabit, CD-ROM, RAM disk veya ağ sürücüsü) belirlenemiyorsa, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için bkz. [parametre doğrulama](../../c-runtime-library/parameter-validation.md).

*arabelleğin*<br/>
Yol için depolama konumu veya **null**.

**Null** belirtilirse, bu işlev, **malloc**kullanarak en az *maxlen* boyut arabelleği ayırır ve **_getdcwd** öğesinin dönüş değeri ayrılan arabelleğin bir işaretçisidir. Arabellek, **serbest** çağırarak ve işaretçi geçirerek serbest bırakılabilirler.

*maxlen*<br/>
, **_Wgetdcwd**için en fazla yolun uzunluk üst sınırını belirten, karakter: **_getdcwd** ve **wchar_t** için **char** .

*Maxlen* değeri sıfıra eşit veya daha küçükse, geçersiz parametre işleyicisi çağrılır. Daha fazla bilgi için bkz. [parametre doğrulama](../../c-runtime-library/parameter-validation.md).

## <a name="return-value"></a>Dönüş Değeri

Belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu temsil eden bir dize işaretçisi veya bir hatayı gösteren **null**.

*Arabellek* **null** olarak belirtilmişse ve *maxlen* karakterleri ayırmak için yeterli bellek yoksa, bir hata oluşur ve **errno** , **ENOMEM**olarak ayarlanır. Sonlandırıcı null karakteri de dahil olmak üzere yolun uzunluğu *maxlen*değerini aşarsa bir hata oluşur ve **errno** , **ERANGE**olarak ayarlanır. Bu hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Getdcwd** işlevi, belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu alır ve *arabelleğe*kaydeder. Geçerli çalışma dizini köke ayarlandıysa, dize bir ters eğik çizgiyle (\\) biter. Geçerli çalışma dizini kök dışında bir dizine ayarlandıysa, dize bir ters eğik çizgiyle değil, dizin adıyla biter.

**_wgetdcwd** , **_getdcwd**öğesinin geniş karakterli bir sürümüdür ve *arabellek* parametresi ve dönüş değeri geniş karakterli dizelerdir. Aksi takdirde, **_wgetdcwd** ve **_getdcwd** aynı şekilde davranır.

Bu işlev, iş parçacığı açısından güvenli olmayan **GetFullPathName**öğesine bağlı olsa da, iş parçacığı açısından güvenlidir. Ancak, çok iş parçacıklı uygulamanız hem bu işlevi hem de [GetFullPathName](/windows/win32/api/fileapi/nf-fileapi-getfullpathnamew)öğesini çağırırsa iş parçacığı güvenliğini ihlal edebilirsiniz.

Bu işlevin **_nolock** sonekine sahip sürümü, iş parçacığı açısından güvenli olmaması ve diğer iş parçacıkları tarafından girişime karşı korunmamaları dışında bu işlevle aynı şekilde davranır. Daha fazla bilgi için bkz. [_getdcwd_nolock, _wgetdcwd_nolock](getdcwd-nolock-wgetdcwd-nolock.md).

**_Debug** ve **_Crtdbg_map_ayırma** tanımlandığında, bellek ayırmalarının hatalarını ayıklayabilmeniz için **_getdcwd** ve **_wgetdcwd** çağrıları **_getdcwd_dbg** ve **_wgetdcwd_dbg** çağrılarıyla değiştirilmiştir. Daha fazla bilgi için bkz.[_getdcwd_dbg, _wgetdcwd_dbg](getdcwd-dbg-wgetdcwd-dbg.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd**|**_getdcwd**|**_getdcwd**|**_wgetdcwd**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdcwd**|\<Direct. h >|
|**_wgetdcwd**|\<Direct. h > veya \<wchar. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Getdrive](getdrive.md)içindeki örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
