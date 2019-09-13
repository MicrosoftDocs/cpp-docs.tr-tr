---
title: _set_abort_behavior
ms.date: 01/02/2018
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
ms.openlocfilehash: b72a485287684fc85f1e232e89774e07a5e3f42b
ms.sourcegitcommit: effb516760c0f956c6308eeded48851accc96b92
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70927485"
---
# <a name="_set_abort_behavior"></a>_set_abort_behavior

Bir program anormal olarak sonlandırıldığı zaman gerçekleştirilecek eylemi belirtir.

> [!NOTE]
> Test veya hata ayıklama senaryoları dışında Microsoft Store uygulamasını kapatmak için [Abort](abort.md) işlevini kullanmayın. Bir mağaza uygulamasını kapatmak için programlı veya Kullanıcı arabirimi yollarına [Microsoft Store ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için bkz. [UWP uygulama yaşam döngüsü](/windows/uwp/launch-resume/app-lifecycle).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Parametreler

*larına*<br/>
[Durdurma](abort.md) bayraklarının yeni değeri.

*maskesi*<br/>
Ayarlanacak [durdurma](abort.md) bayrakları bitlerinin maskesi.

## <a name="return-value"></a>Dönüş Değeri

Bayrakların eski değeri.

## <a name="remarks"></a>Açıklamalar

İki [iptal](abort.md) bayrağı vardır: **_WRITE_ABORT_MSG** ve **_call_reportfault**. **_WRITE_ABORT_MSG** , bir program anormal olarak sonlandırıldığı zaman bir faydalı metin mesajının yazdırılıp yazdırılmadığını belirler. İleti, uygulamanın [Abort](abort.md) işlevini çağırdığını belirtir. Varsayılan davranış, iletiyi yazdırdır. **_Call_reportfault**, ayarlanırsa, [Iptal](abort.md) çağrıldığında bir Watson kilitlenme dökümünün oluşturulup bildirildiğini belirtir. Varsayılan olarak, kilitlenme bilgi döküm raporlaması hata ayıklama olmayan derlemelerde etkindir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_abort_behavior**|\<Stdlib. h >|

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
