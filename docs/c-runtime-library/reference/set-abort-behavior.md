---
title: _set_abort_behavior
ms.date: 1/02/2018
apiname:
- _set_abort_behavior
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_abort_behavior
- set_abort_behavior
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
ms.openlocfilehash: 8b36a771a3694c6d01573d619990743c7ddc0f3e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643059"
---
# <a name="setabortbehavior"></a>_set_abort_behavior

Bir program anormal olarak sonlandırıldığında gerçekleştirilecek eylemi belirtir.

> [!NOTE]
> Kullanmayın [iptal](abort.md) test veya hata ayıklama senaryoları dışında bir Microsoft Store uygulamasını kapatmak için işlevi. Bir Store uygulamasını kapatmak için programlama veya UI yollarına göre izin verilmez [Microsoft Store ilkeleri](/legal/windows/agreements/store-policies). Daha fazla bilgi için [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Parametreler

*bayrakları*<br/>
Yeni değeri [iptal](abort.md) bayrakları.

*Maskesi*<br/>
İçin maske [iptal](abort.md) ayarlamak için bit bayrakları.

## <a name="return-value"></a>Dönüş Değeri

Bayrakların eski değeri.

## <a name="remarks"></a>Açıklamalar

İki [iptal](abort.md) bayraklar: **_WRITE_ABORT_MSG** ve **_CALL_REPORTFAULT**. **_WRITE_ABORT_MSG** bir program anormal olarak sonlandırıldığında yardımcı bir metin iletisinin yazdırılıp yazdırılmayacağını belirler. İletiyi bildiren uygulama çağırdı [iptal](abort.md) işlevi. İletiyi yazdırmak için varsayılan davranıştır. **_CALL_REPORTFAULT**, ayarla, Watson kilitlenme dökümünün oluşturulduğunu ve raporlandığını belirtir [iptal](abort.md) çağrılır. Varsayılan olarak kilitlenme bilgi dökümü raporlaması DEBUG olmayan yapılarda etkinleştirilir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[abort](abort.md)<br/>
