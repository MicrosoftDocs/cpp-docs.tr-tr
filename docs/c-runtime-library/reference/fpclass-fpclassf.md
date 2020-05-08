---
title: _fpclass, _fpclassf
ms.date: 4/2/2020
api_name:
- _fpclass
- _fpclassf
- _o__fpclass
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
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
ms.openlocfilehash: a6591d9348739d27831785a05f4a602aacdd4d0c
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914840"
---
# <a name="_fpclass-_fpclassf"></a>_fpclass, _fpclassf

Bağımsız değişkenin kayan nokta sınıflandırmasını gösteren bir değer döndürür.

## <a name="syntax"></a>Sözdizimi

```C
int _fpclass(
   double x
);

int _fpclassf(
   float x
); /* x64 only */
```

### <a name="parameters"></a>Parametreler

*sayı*<br/>
Sınanacak kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**_Fpclass** ve **_fpclassf** işlevleri, *x*bağımsız değişkeninin kayan nokta sınıflandırmasını gösteren bir tamsayı değeri döndürür. Sınıflandırma, \<float. h> tanımlanmış aşağıdaki değerlerden birine sahip olabilir.

|Değer|Açıklama|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Sinyal NaN|
|**_FPCLASS_QNAN**|Sessiz NaN|
|**_FPCLASS_NINF**|Negatif sonsuzluk (-INF)|
|**_FPCLASS_NN**|Negatif normalleştirilmiş sıfır olmayan|
|**_FPCLASS_ND**|Negatif Normalleştirilmemiş|
|**_FPCLASS_NZ**|Negatif sıfır (-0)|
|**_FPCLASS_PZ**|Pozitif 0 (+ 0)|
|**_FPCLASS_PD**|Olumlu olarak yoğun|
|**_FPCLASS_PN**|Pozitif normalleştirilmiş sıfır olmayan|
|**_FPCLASS_PINF**|Pozitif sonsuzluk (+ INF)|

## <a name="remarks"></a>Açıklamalar

**_Fpclass** ve **_fpclassf** işlevleri Microsoft 'a özgüdür. [Fpsınıflandır](fpclassify.md)benzerdir, ancak bağımsız değişkenle ilgili daha ayrıntılı bilgiler döndürür. **_Fpclassf** işlevi yalnızca x64 platformu için derlendikleri zaman kullanılabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float. h>|

Daha fazla uyumluluk ve uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>
