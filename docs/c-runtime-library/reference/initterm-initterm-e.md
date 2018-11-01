---
title: _initterm, _initterm_e
ms.date: 11/04/2016
apiname:
- _initterm_e
- _initterm
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
- _initterm_e
- initterm
- _initterm
- initterm_e
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
ms.openlocfilehash: 65963e95507d4d6444ebcc9038b5b8cf797f9feb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620720"
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e

İşlev işaretçileri tablosu izlemek ve bunları başlatmak iç yöntemler.

İlk işaretçi tablosundaki Başlangıç konumu ve ikinci işaretçi bitiş konumu.

## <a name="syntax"></a>Sözdizimi

```C
void __cdecl _initterm(
   PVFV *,
   PVFV *
);

int __cdecl _initterm_e(
   PVFV *,
   PVFV *
);
```

## <a name="return-value"></a>Dönüş Değeri

Bir sıfır olmayan hata kodu; bir başlatma başarısız olursa ve bir hata oluşturur Eğer hiç Hata oluşmazsa 0.

## <a name="remarks"></a>Açıklamalar

Bu yöntemler, yalnızca C++ program başlatma sırasında dahili olarak adlandırılır. Bu yöntemler bir programda çağırmayın.

Bu yöntemler bir tablo işlevi girişlerinin yol, bunlar atla **NULL** girişleri ve devam edin.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
