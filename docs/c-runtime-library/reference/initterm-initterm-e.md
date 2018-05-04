---
title: _initterm, _initterm_e | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- initterm function
- initterm_e function
- _initterm function
- _initterm_e function
ms.assetid: 85131efe-c747-429a-8897-bcdedb000172
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 470ad6cbf13efb170f61aa12f7859f2baa248c2b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="initterm-initterme"></a>_initterm, _initterm_e

İşlev işaretçileri tablosu yol ve bunları başlatma iç yöntemleri.

Başlangıç konumu tablosundaki ilk işaretçidir ve ikinci işaretçisi bitiş konumu.

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

Bir başlatma başarısız olduğunda ve bir hata oluşturur sıfır olmayan bir hata kodu; 0 hata oluşmaz.

## <a name="remarks"></a>Açıklamalar

Bu yöntemleri yalnızca bir C++ program başlatma sırasında dahili olarak adlandırılır. Bu yöntemler bir programda çağırmayın.

Bu yöntemler bir tablosu işlevi girdileri yol, bunlar atla **NULL** girişleri ve devam edin.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
