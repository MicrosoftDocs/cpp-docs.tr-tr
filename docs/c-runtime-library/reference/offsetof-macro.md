---
title: offsetof makrosu
ms.date: 11/04/2016
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
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: a0f367dbe6fa2681a7d413304f32b5699b8f7cee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156079"
---
# <a name="offsetof-macro"></a>offsetof makrosu

Kendi ana yapısının başlangıcından itibaren bir üyenin uzaklığını alır.

## <a name="syntax"></a>Sözdizimi

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Parametreler

*structName*<br/>
Üst verileri yapının adı.

*memberName*<br/>
Uzaklık belirlemek için ana veri yapısı içinde bir üyesinin adı.

## <a name="return-value"></a>Dönüş Değeri

**offsetof** uzaklık üst veri yapısının başlangıcından itibaren belirtilen üyenin bayt cinsinden döndürür. Bit alanları için tanımlanmamıştır.

## <a name="remarks"></a>Açıklamalar

**Offsetof** makrosu bayt cinsinden uzaklığı döndürür *memberName* tarafından belirtilen yapısının başlangıcından *structName* türünde bir değer olarak **size_ t**. Türleriyle belirtebilirsiniz **yapı** anahtar sözcüğü.

> [!NOTE]
> **offsetof** bir işlev değil ve bir C prototipi kullanarak açıklanan olamaz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**offsetof**|\<stddef.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
