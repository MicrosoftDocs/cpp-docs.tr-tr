---
title: _set_abort_behavior
ms.date: 4/2/2020
api_name:
- _set_abort_behavior
- _o__set_abort_behavior
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: fd3a3c2f99d1702cdccf68328c2122b965b2d078
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81337876"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

Bir program anormal şekilde sonlandırıldığında yapılacak eylemi belirtir.

> [!NOTE]
> Test veya hata ayıklama senaryoları dışında bir Microsoft Mağazası uygulamasını kapatmak için [iptal](abort.md) işlevini kullanmayın. Bir Mağaza uygulamasını kapatmanın programlı veya uI yollarına [Microsoft Mağazası ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için [UWP uygulama yaşam döngüsüne](/windows/uwp/launch-resume/app-lifecycle)bakın.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Parametreler

*bayraklar*<br/>
[İptal](abort.md) bayraklarının yeni değeri.

*maske*<br/>
İptal [bayrakları](abort.md) bitlerinin ayarlanışması için maske.

## <a name="return-value"></a>Dönüş Değeri

Bayrakların eski değeri.

## <a name="remarks"></a>Açıklamalar

İki [iptal](abort.md) bayrağı vardır: **_WRITE_ABORT_MSG** ve **_CALL_REPORTFAULT.** **_WRITE_ABORT_MSG,** bir program anormal şekilde sonlandırıldığında yararlı bir metin iletisi yazdırılıp yazdırılmadığını belirler. İleti, uygulamanın [iptal](abort.md) işlevini çağırdığını belirtir. Varsayılan davranış iletiyi yazdırmaktır. **_CALL_REPORTFAULT,** eğer ayarlanırsa, Watson kilitlenme dökümü oluşturulur ve [iptal](abort.md) çağrıldığında rapor belirtir. Varsayılan olarak, hata ayıklama bildirimi hata ayıklama olmayan yapılarda etkinleştirilir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_set_abort_behavior.c
// compile with: /TC
#include <stdlib.h>

int main()
{
   printf("Suppressing the abort message. If successful, this message"
          " will be the only output.\n");
   // Suppress the abort message
   _set_abort_behavior( 0, _WRITE_ABORT_MSG);
   abort();
}
```

```Output
Suppressing the abort message. If successful, this message will be the only output.
```

## <a name="see-also"></a>Ayrıca bkz.

[Iptal](abort.md)<br/>
