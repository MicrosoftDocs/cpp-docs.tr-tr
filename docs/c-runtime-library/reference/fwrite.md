---
title: fwrite
ms.date: 4/2/2020
api_name:
- fwrite
- _o_fwrite
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
- fwrite
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
ms.openlocfilehash: a5bd6da3c8d16189f7ff0db744901e03513acc21
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345403"
---
# <a name="fwrite"></a>fwrite

Akışına veri yazar.

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

*Arabellek*<br/>
Yazılacak verilere işaretçi.

*Boyutu*<br/>
Madde boyutu, baytlar halinde.

*Sayısı*<br/>
Yazılacak maksimum öğe sayısı.

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

## <a name="return-value"></a>Dönüş Değeri

**fwrite,** bir hata oluşursa *sayısı* daha az olabilir, gerçekten yazılmış tam öğelerin sayısını döndürür. Ayrıca, bir hata oluşursa, dosya konumu göstergesi belirlenemez. *Akış* veya *arabellek* null işaretçisi ise veya yazılacak tek sayıda bayt Unicode modunda belirtiliyorsa, işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin verilirse, bu işlev **errno'u** **EINVAL'e** ayarlar ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Fwrite** işlevi, *arabellekten* çıkış *akışına*kadar her biri *boyut* uzunluğu olan öğeleri *saymak* için yazar. *Akışla* ilişkili dosya işaretçisi (varsa) gerçekte yazılan bayt sayısına göre artımlanır. *Akış* metin modunda açılırsa, her satır akışı bir satır satır satır besleme çifti ile değiştirilir. Değiştirmenin iade değeri üzerinde hiçbir etkisi yoktur.

*Akış* Unicode çeviri modunda açıldığında-örneğin, *akış* **fopen'i** arayarak ve **ccs=UNICODE**, **ccs=UTF-16LE**veya **ccs=UTF-8**içeren bir mod parametresi kullanılarak açılırsa veya mod **_setmode** kullanılarak Unicode çeviri moduna değiştirilirse ve **_O_WTEXT**içeren bir mod parametresi , **_O_U16TEXT**, veya **_O_U8TEXT**-*arabellek* UTF 16 veri içeren bir dizi **wchar_t** için işaretçi olarak yorumlanır. Bu modda tek sayıda bayt yazma girişimi parametre doğrulama hatasına neden olur.

Bu işlev arama iş parçacığı kilitlediği için iş parçacığı güvenlidir. Kilitlenmeyen bir sürüm için **bkz. _fwrite_nolock.**

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Fread](fread.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
