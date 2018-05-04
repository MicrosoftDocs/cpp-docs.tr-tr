---
title: fwrite | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- streams, writing data to
- fwrite function
ms.assetid: 7afacf3a-72d7-4a50-ba2e-bea1ab9f4124
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1320bcc61830833f2b1a4a225dff30652df2d3a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
Yazılacak veriler işaretçi.

*Boyutu*<br/>
Bayt olarak öğe boyutu.

*Sayısı*<br/>
Yazılacak öğe maksimum sayısı.

*Akış*<br/>
İşaretçi **dosya** yapısı.

## <a name="return-value"></a>Dönüş Değeri

**fwrite** tam sayısını döndürür gerçekte yazılan öğeleri, hangi olabilir değerinden *sayısı* bir hata oluşursa. Ayrıca, bir hata oluşursa, dosya konumu göstergesi belirlenemiyor. Her iki *akış* veya *arabellek* null işaretçi veya tek sayıda yazılacak bayt Unicode modda belirtilirse, işlevi geçersiz parametre işleyicisi açıklandığı gibi çağırır [ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve 0 döndürür.

## <a name="remarks"></a>Açıklamalar

**Fwrite** işlevi Yazar kadar *sayısı* öğeleri, *boyutu* uzunluğu her gelen *arabellek* çıktısına *akış*. İle ilişkili dosya işaretçisini *akış* (varsa) tarafından gerçekten yazılan bayt sayısı artar. Varsa *akış* açıldığında metin modunda bir satır başı ile - satır besleme çifti her satır besleme değiştirilir. Değiştirme dönüş değeri üzerinde etkisi yoktur.

Zaman *akış* Unicode çeviri modunda açılmış — Örneğin, varsa *akış* çağırarak açılan **fopen** ve içeren bir mod parametresini kullanarak **ccs = UNICODE**, **ccs UTF-16LE =**, veya **ccs = UTF-8**, veya modunu kullanarak bir Unicode çeviri modu değiştirilirse **_setmode** ve modu içeren parametre **_O_WTEXT**, **_O_U16TEXT**, veya **_O_U8TEXT**—*arabellek* gösteren bir işaretçi olarak yorumlanır bir dizi **wchar_t** UTF-16 verileri içerir. Bu modda tek sayıda bayt yazma girişimi bir parametre doğrulama hatasına neden olur.

Bu işlev çağıran iş parçacığı kilitler, iş parçacığı demektir. Kilitleme olmayan bir sürümü için bkz: **_fwrite_nolock**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fwrite**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [fread](fread.md).

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_setmode](setmode.md)<br/>
[fread](fread.md)<br/>
[_fwrite_nolock](fwrite-nolock.md)<br/>
[_write](write.md)<br/>
