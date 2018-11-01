---
title: fclose, _fcloseall
ms.date: 11/04/2016
apiname:
- fclose
- _fcloseall
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fclose
- _fcloseall
helpviewer_keywords:
- fclose function
- streams, closing
- _fcloseall function
ms.assetid: c3c6ea72-92c6-450a-a33e-3e568d2784a4
ms.openlocfilehash: 4713ffb7ecdf8da73e5f949bbef7be124dfaf28a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536519"
---
# <a name="fclose-fcloseall"></a>fclose, _fcloseall

Bir akışı kapatır (**fclose**) veya tüm açık akışları kapatır (**_fcloseall**).

## <a name="syntax"></a>Sözdizimi

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fclose** akışın başarılı bir şekilde kapanırsa, 0 döndürür. **_fcloseall** Akış kapalı toplam sayısını döndürür. Her iki işlev dönüş **EOF** bir hatayı göstermek için.

## <a name="remarks"></a>Açıklamalar

**Fclose** işlev kapanır *stream*. Varsa *stream* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **fclose** ayarlar **errno** için **EINVAL** ve döndürür **EOF**. Önerilir *stream* işaretçisi her zaman kullanıma bu işlevi çağırmadan önce.

Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.

**_Fcloseall** işlevi hariç tüm açık akışları kapatır **stdin**, **stdout**, **stderr** (ve MS-DOS **_stdaux**  ve **_stdprn**). Ayrıca kapatır ve siler tarafından oluşturulan geçici dosyalar **tmpfile**. Her iki işlev stream ile ilişkili tüm arabellekler kapatmadan önce temizlenir. Akış kapalıyken, sistem tarafından ayrılan arabellekler serbest bırakılır. Arabellek ile kullanıcı tarafından atanan **setbuf** ve **setvbuf** değil otomatik olarak yayımlanır.

**Not:** bu işlevler, bir akış kapatmak için kullanıldığında, temel alınan dosya tanımlayıcısı ve işletim sistemi dosya tanıtıcısı (veya yuva), yanı sıra stream kapatılır. Bu nedenle, dosyanın ilk açıldığı bir dosya olarak işlemek veya dosya tanımlayıcısı ve ile kapalı **fclose**, çağrı değil de yapmanız **_close** için dosya tanımlayıcıyı kapatın; Win32 işlevini çağırmayın  **CloseHandle** dosya tanıtıcısı kapatın.

**fclose** ve **_fcloseall** diğer iş parçacıklarından kesintiye karşı korumak için kod içerir. Kilitleme yapılmayan bir sürüm için bir **fclose**, bkz: **_fclose_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fclose**|\<stdio.h >|
|**_fcloseall**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [fopen](fopen-wfopen.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
