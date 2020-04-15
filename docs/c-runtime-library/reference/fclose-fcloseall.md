---
title: fclose, _fcloseall
ms.date: 4/2/2020
api_name:
- fclose
- _fcloseall
- _o__fcloseall
- _o_fclose
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b2ee14c5fc8bb47cc2652443c0263bd14147c90d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347486"
---
# <a name="fclose-_fcloseall"></a>fclose, _fcloseall

Bir akışı kapatır **(fclose)** veya tüm açık akışları kapatır **(_fcloseall).**

## <a name="syntax"></a>Sözdizimi

```C
int fclose(
   FILE *stream
);
int _fcloseall( void );
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

akış başarıyla kapatılırsa **fclose** 0 döndürür. **_fcloseall,** kapatılan toplam akış sayısını döndürür. Her iki işlev de hata göstermek için **EOF** döndürer.

## <a name="remarks"></a>Açıklamalar

**Fclose** işlevi *akışı*kapatır. *Akış* **NULL**ise, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **fclose** Setleri **ErrNO** **EINVAL** ve **EOF**döndürür. Akış işaretçisinin *stream* bu işlevi çağırmadan önce her zaman denetlenebilen önerilir.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın.

**_fcloseall** işlevi **stdin**, **stdout**, **stderr** (ve MS-DOS, **_stdaux** ve **_stdprn**hariç tüm açık akışları kapatır). Ayrıca **tmpfile**tarafından oluşturulan geçici dosyaları kapatır ve siler. Her iki işlevde de, akışla ilişkili tüm arabellekler kapanmadan önce temizlenir. Akış kapatıldığında sistem tarafından ayrılan arabellekler serbest bırakılır. Kullanıcı tarafından **setbuf** ve **setvbuf** ile atanan arabellekler otomatik olarak serbest bırakılmaz.

**Not:** Bu işlevler bir akışı kapatmak için kullanıldığında, temel dosya tanımlayıcısı ve işletim sistemi dosya tutamacı (veya soket) ve akış kapatılır. Bu nedenle, dosya başlangıçta bir dosya tutamacı veya dosya tanımlayıcısı olarak açılmışsa ve **fclose**ile kapatılırsa, dosya tanımlayıcısını kapatmak için **_close** de aramayın; Dosya tutamacını kapatmak için Win32 işlevini **CloseHandle** olarak aramayın.

**fclose** ve **_fcloseall** diğer iş parçacıkları girişime karşı korumak için kod içerir. Bir **fclose**olmayan kilitleme sürümü için, **_fclose_nolock**bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Fclose**|\<stdio.h>|
|**_fcloseall**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Fopen](fopen-wfopen.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_close](close.md)<br/>
[_fdopen, _wfdopen](fdopen-wfdopen.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[freopen, _wfreopen](freopen-wfreopen.md)<br/>
