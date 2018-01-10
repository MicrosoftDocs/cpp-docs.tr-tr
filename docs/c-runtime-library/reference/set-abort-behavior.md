---
title: _set_abort_behavior | Microsoft Docs
ms.custom: 
ms.date: 1/02/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_abort_behavior
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
dev_langs: C++
helpviewer_keywords:
- aborting programs
- _set_abort_behavior function
- set_abort_behavior function
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 965ff160fd8098c60f53f639cb95aedf890edd86
ms.sourcegitcommit: a5d8f5b92cb5e984d5d6c9d67fe8a1241f3fe184
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/05/2018
---
# <a name="setabortbehavior"></a>_set_abort_behavior

Bir program anormal olduğunda gerçekleştirilecek eylemi belirtir.

> [!NOTE]
> Kullanmayın `abort` test veya senaryoları hata ayıklama bir Microsoft Store uygulamasını, kapatmak için işlevi. Bir mağaza uygulamasını kapatmak için programlı veya UI yolu göre verilmez [Microsoft Store ilkeleri](http://go.microsoft.com/fwlink/?LinkId=865936). Daha fazla bilgi için bkz: [UWP uygulama yaşam döngüsü](http://go.microsoft.com/fwlink/p/?LinkId=865934).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _set_abort_behavior(
   unsigned int flags,
   unsigned int mask
);
```

### <a name="parameters"></a>Parametreler

[in] _bayrakları_  
Yeni değeri `abort` bayrakları.

[in] _maskesi_  
İçin maske `abort` ayarlamak için BITS işaretler.

## <a name="return-value"></a>Dönüş Değeri

Bayrakları eski değeri.

## <a name="remarks"></a>Açıklamalar

Var olan iki `abort` bayrakları: `_WRITE_ABORT_MSG` ve `_CALL_REPORTFAULT`. `_WRITE_ABORT_MSG`bir program anormal olduğunda yararlı kısa mesaj yazdırılan olup olmadığını belirler. İleti durumları uygulama çağırdı `abort` işlevi. İleti yazdırmak için varsayılan davranıştır. `_CALL_REPORTFAULT`, varsa, otomatik olarak bir Watson kilitlenme döküm oluşturulur ve ne zaman rapor belirtir `abort` olarak adlandırılır. Varsayılan olarak, kilitlenme döküm raporlama olmayan hata ayıklama derlemelerinde etkindir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`_set_abort_behavior`|\<stdlib.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[abort](../../c-runtime-library/reference/abort.md)  
