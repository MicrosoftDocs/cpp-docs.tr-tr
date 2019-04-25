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
ms.openlocfilehash: b4d6b9ce4fb66ee545f52946e28e4984d9e4f924
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287553"
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

*Arabellek*<br/>
Yazılacak veri işaretçisi.

*Boyutu*<br/>
Bayt olarak öğe boyutu.

*Sayısı*<br/>
Yazılacak öğe maksimum sayısı.

*Stream*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fwrite** tam döndürür öğeleri, gerçekte yazılan gösterebilir küçüktür *sayısı* hata oluşması durumunda. Ayrıca, bir hata oluşursa, dosya konumu göstergesi belirlenemiyor. Ya da *stream* veya *arabellek* null bir işaretçiyse veya tek sayıda bayt yazılacak Unicode modunda belirtilirse, işlev geçersiz parametre işleyicisi açıklandığı gibi çağırır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Fwrite** işlevi Yazar kadar *sayısı* öğeleri, *boyutu* uzunluğu her gelen *arabellek* çıktısına *stream*. İle ilişkili dosya işaretçisini *stream* (varsa) gerçekte yazılan bayt sayısına göre artırılır. Varsa *stream* açıldığında metin modunda bir satır başı ile - satır besleme çifti her satır besleme değiştirilir. Değiştirme dönüş değeri üzerinde etkisi yoktur.

Zaman *stream* Unicode çeviri modunda açıldığında — Örneğin, varsa *stream* çağırarak açıldığında **fopen** ve içeren bir mode parametresi kullanarak **ccs = UNICODE**, **ccs UTF-16LE =**, veya **ccs = UTF-8**, veya modu kullanılarak bir Unicode çeviri moduna değiştirilirse **_setmode** ve modu içeren parametre **_O_WTEXT**, **_O_U16TEXT**, veya **_O_U8TEXT**—*arabellek* işaretçisi olarak yorumlanan bir dizi **wchar_t** , UTF-16 verileri içerir. Bu modda tek sayıda bayt yazma girişimi, bir parametre doğrulama hatasına neden olur.

Bu işlevi çağıran iş parçacığının kilitler, iş parçacığı açısından güvenli olmasıdır. Kilitleme yapılmayan bir sürüm için bkz. **_fwrite_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwrite**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [fread](fread.md).

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
