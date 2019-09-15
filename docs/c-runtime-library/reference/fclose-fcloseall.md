---
title: fclose, _fcloseall
ms.date: 11/04/2016
api_name:
- fclose
- _fcloseall
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 215925fb16f5d51e481ae92cbb45b0270bd5ebd4
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70941499"
---
# <a name="fclose-_fcloseall"></a>fclose, _fcloseall

Bir akışı (**fclose**) kapatır veya tüm açık akışları ( **_fcloseall**) kapatır.

## <a name="syntax"></a>Sözdizimi

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

Akış başarıyla kapatılırsa, **fclose** 0 döndürür. **_fcloseall** , kapatılan toplam akış sayısını döndürür. Her iki işlev de bir hatayı göstermek için **EOF** döndürür.

## <a name="remarks"></a>Açıklamalar

**Fclose** işlevi *akışı*kapatır. *Stream* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **fclose** , **errno** , **EINVAL** olarak ayarlar ve **EOF**döndürür. Bu işlev çağrılmadan önce *akış* işaretçisinin her zaman denetlenmesi önerilir.

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) .

**_Fcloseall** işlevi, **stdin**, **stdout**, **stderr** (ve ile MS-DOS, **_stdadux** ve **_stdprn**) dışındaki tüm açık akışları kapatır. Ayrıca, **tmpfile**tarafından oluşturulan geçici dosyaları da kapatır ve siler. Her iki durumda da, akışla ilişkili tüm arabellekler kapatılmadan önce temizlenir. Sistem tarafından ayrılan arabellekler, Akış kapalıyken serbest bırakılır. Kullanıcı tarafından **setarabelleğe** ve **setvarabelleğe** atanan arabellekler otomatik olarak serbest bırakılır.

**Not:** Bu işlevler bir akışı kapatmak için kullanıldığında, arka plandaki dosya tanımlayıcısının ve işletim sistemi dosya tutamacının (veya yuvasının) yanı sıra akışı da kapanır. Bu nedenle, dosya başlangıçta bir dosya tutamacı veya dosya tanımlayıcısı olarak açılırsa ve **fclose**ile kapatılırsa, dosya tanımlayıcısını kapatmak için **_close** 'u de çağırmayın; dosya tanıtıcısını kapatmak için **CloseHandle** Win32 işlevini çağırmayın.

**fclose** ve **_fcloseall** , diğer iş parçacıklarından gelen girişimlere karşı korumak için kod içerir. Bir **fclose**'un kilitleme dışı sürümü için, bkz. **_fclose_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fclose**|\<stdio. h >|
|**_fcloseall**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Fopen](fopen-wfopen.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
