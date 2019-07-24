---
title: fwrite
ms.date: 11/04/2016
apiname:
- fwrite
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
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: f05e39390f3a2d0ad41627f6aed1aecd77b57cca
ms.sourcegitcommit: 878a164fe6d550ca81ab87d8425c8d3cd52fe384
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68376058"
---
# <a name="fwrite"></a>fwrite

Verileri bir akışa yazar.

## <a name="syntax"></a>Sözdizimi

```C
size_t fwrite(
   const void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Yazılacak veri işaretçisi.

*boyutla*<br/>
Öğe boyutu (bayt).

*biriktirme*<br/>
Yazılacak en fazla öğe sayısı.

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**fwrite** , gerçekten yazılmış olan tam öğe sayısını döndürür ve bir hata oluşursa *Count* 'tan daha az olabilir. Ayrıca, bir hata oluşursa, dosya konumu göstergesi belirlenemez. *Stream* veya *buffer* bir null işaretçisiyse veya Unicode modunda yazılabilir tek sayıda bayt belirtilirse, işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Fwrite** işlevi, sayı *uzunluğunun her* biri, *arabelleğe* çıkış *akışına*kadar olan öğeleri *say* için yazar. *Stream* ile ilişkili dosya işaretçisi (varsa), gerçekten yazılan bayt sayısıyla artırılır. *Akış* metin modunda açılırsa, her satır akışı bir satır başı satır besleme çiftiyle değiştirilmiştir. Değiştirme işleminin dönüş değeri üzerinde hiçbir etkisi yoktur.

*Akış* Unicode çeviri modunda açıldığında — Örneğin, *Stream* , **fopen** çağırarak ve **CCS = UNICODE**, **CCS = UTF-16LE**, ya da **CCS = UTF-8**' i içeren bir mod parametresi kullanılarak açılırsa veya mod ise **_setmode** ve  **_O_WTEXT**, **_O_u16text**veya **_O_U8TEXT**— içeren bir mod parametresi kullanılarak bir Unicode çeviri moduna,*arabellek* , UTF-16 verileri. Bu modda tek sayıda bayt yazma girişimi bir parametre doğrulama hatasına neden olur.

Bu işlev çağıran iş parçacığını kilitlediği için iş parçacığı güvenlidir. Kilitleme dışı bir sürüm için bkz. **_fwrite_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwrite**|\<stdio. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Fread](fread.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
