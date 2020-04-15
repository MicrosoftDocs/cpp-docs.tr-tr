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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: b16655fed046114e9dd8592c5e1fd3fc5f7ed4bf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346287"
---
# <a name="_fpclass-_fpclassf"></a>_fpclass, _fpclassf

Bağımsız değişkenin kayan nokta sınıflandırmasını gösteren bir değer verir.

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

*X*<br/>
Test etmek için kayan nokta değeri.

## <a name="return-value"></a>Dönüş Değeri

**_fpclass** ve **_fpclassf** *işlevleri, x*bağımsız değişkeninin kayan nokta sınıflandırmasını gösteren bir tamsayı değeri döndürmektedir. Sınıflandırma, \<float.h> tanımlanan aşağıdaki değerlerden birine sahip olabilir.

|Değer|Açıklama|
|-----------|-----------------|
|**_FPCLASS_SNAN**|Sinyal NaN|
|**_FPCLASS_QNAN**|Sessiz Nan|
|**_FPCLASS_NINF**|Negatif sonsuzluk ( -INF)|
|**_FPCLASS_NN**|Negatif normalleştirilmiş sıfır sız|
|**_FPCLASS_ND**|Negatif denormalized|
|**_FPCLASS_NZ**|Negatif sıfır ( - 0)|
|**_FPCLASS_PZ**|Pozitif 0 (+0)|
|**_FPCLASS_PD**|Pozitif denormalize|
|**_FPCLASS_PN**|Pozitif normalleştirilmiş sıfır sız|
|**_FPCLASS_PINF**|Pozitif sonsuzluk (+INF)|

## <a name="remarks"></a>Açıklamalar

**_fpclass** ve **_fpclassf** işlevleri Microsoft'a özgüdir. Bunlar [fpclassify](fpclassify.md)benzer, ancak bağımsız değişken hakkında daha ayrıntılı bilgi döndürün. **_fpclassf** işlevi yalnızca x64 platformu için derlendiğinde kullanılabilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_fpclass**, **_fpclassf**|\<float.h>|

Daha fazla uyumluluk ve uyumluluk bilgisi için [bkz.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[fpclassify](fpclassify.md)<br/>
