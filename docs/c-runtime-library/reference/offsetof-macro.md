---
title: offsetof makrosu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- offsetof
dev_langs:
- C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 308aac2493751cfe2147187ed9848347124a90d6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32401470"
---
# <a name="offsetof-macro"></a>offsetof makrosu

Uzaklık üyenin üst yapısını baştan alır.

## <a name="syntax"></a>Sözdizimi

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Parametreler

*structName*<br/>
Ana veri yapısı adı.

*memberName*<br/>
Uzaklık belirlemek için ana veri yapısı üye adı.

## <a name="return-value"></a>Dönüş Değeri

**offsetof** uzaklık belirtilen üye bayt cinsinden üst veri yapısını baştan döndürür. Bit alanları için tanımlı değil.

## <a name="remarks"></a>Açıklamalar

**Offsetof** makrosu bayt cinsinden uzaklık döndürür *memberName* tarafından belirtilen yapısı başından itibaren *structName* türünde bir değer olarak **size_ t**. Türleriyle belirtebilirsiniz **yapısı** anahtar sözcüğü.

> [!NOTE]
> **offsetof** C prototipi kullanarak açıklanan olamaz ve bir işlev değil.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**offsetof**|\<stddef.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
