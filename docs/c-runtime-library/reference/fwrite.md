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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: b604819391629d057850c17466807e7c329c472d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87198599"
---
# <a name="fwrite"></a>fwrite

Verileri bir akışa yazar.

## <a name="syntax"></a>Söz dizimi

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

**Fwrite** işlevi, sayı *uzunluğunun her biri,* *arabelleğe* çıkış *akışına*kadar olan öğeleri *say* için yazar. *Stream* ile ilişkili dosya işaretçisi (varsa), gerçekten yazılan bayt sayısıyla artırılır. *Akış* metin modunda açılırsa, her satır akışı bir satır başı satır besleme çiftiyle değiştirilmiştir. Değiştirme işleminin dönüş değeri üzerinde hiçbir etkisi yoktur.

*Akış* Unicode çeviri modunda açıldığında — Örneğin, *Stream* , **fopen** çağırarak ve **CCS = UNICODE**içeren BIR Mode PARAMETRESI kullanılarak açılırsa **CCS = UTF-16LE**veya **ccs = UTF-8**veya mod, **_O_WTEXT**, **_O_U16TEXT**veya **_O_U8TEXT**içeren bir mod parametresi **_setmode** kullanarak bir Unicode çeviri moduna değiştirildiyse,*Ara bellek* , **`wchar_t`** UTF-16 verileri içeren bir Array işaretçisi olarak yorumlanır. Bu modda tek sayıda bayt yazma girişimi bir parametre doğrulama hatasına neden olur.

Bu işlev çağıran iş parçacığını kilitlediği için iş parçacığı güvenlidir. Kilitleme dışı bir sürüm için bkz. **_fwrite_nolock**.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwrite**|\<stdio.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Fread](fread.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
