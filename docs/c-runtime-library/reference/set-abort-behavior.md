---
description: 'Hakkında daha fazla bilgi edinin: _set_abort_behavior'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 1e024cf825115204f51e727d81af7aba74c305fb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288912"
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

*bayraklar*<br/>
[Durdurma](abort.md) bayraklarının yeni değeri.

*maske*<br/>
Ayarlanacak [durdurma](abort.md) bayrakları bitlerinin maskesi.

## <a name="return-value"></a>Dönüş Değeri

Bayrakların eski değeri.

## <a name="remarks"></a>Açıklamalar

İki [iptal](abort.md) bayrağı vardır: **_WRITE_ABORT_MSG** ve **_CALL_REPORTFAULT**. **_WRITE_ABORT_MSG** , bir program anormal olarak sonlandırıldığı zaman yararlı bir metin mesajının yazdırılıp yazdırılmadığını belirler. İleti, uygulamanın [Abort](abort.md) işlevini çağırdığını belirtir. Varsayılan davranış, iletiyi yazdırdır. **_CALL_REPORTFAULT**, ayarlandıysa, bir Watson kilitlenme dökümünün oluşturulduğunu ve [durdurma](abort.md) çağrıldığında rapor oluşturulacağını belirtir. Varsayılan olarak, kilitlenme bilgi döküm raporlaması hata ayıklama olmayan derlemelerde etkindir.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_abort_behavior**|\<stdlib.h>|

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

[durdur](abort.md)<br/>
