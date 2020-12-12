---
description: 'Hakkında daha fazla bilgi edinin: _initterm _initterm_e'
title: _initterm, _initterm_e
ms.date: 11/04/2016
api_name:
- _initterm_e
- _initterm
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
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: c9686504ae39f5aad1678430f4e4ad0054aabc36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296400"
---
# <a name="_initterm-_initterm_e"></a>_initterm, _initterm_e

İşlev işaretçilerinin bir tablosunu sunan ve bunları başlatacak iç Yöntemler.

İlk işaretçi, tablodaki başlangıç konumu ve ikinci işaretçi ise bitiş konumudur.

## <a name="syntax"></a>Syntax

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

Bir başlatma başarısız olursa sıfır olmayan bir hata kodu, bir hata oluşturur; herhangi bir hata oluşursa 0.

## <a name="remarks"></a>Açıklamalar

Bu yöntemler yalnızca bir C++ programının başlatılması sırasında dahili olarak çağırılır. Bu yöntemleri bir programda çağırmayın.

Bu yöntemler bir işlev girdileri tablosu üzerinde gezinirken, **null** girişleri atlar ve devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Alfabetik İşlev Başvurusu](crt-alphabetical-function-reference.md)<br/>
