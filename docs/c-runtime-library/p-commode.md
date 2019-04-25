---
title: __p__commode
ms.date: 11/04/2016
apiname:
- __p__commode
apilocation:
- msvcr110.dll
- msvcrt.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- __p__commode
helpviewer_keywords:
- __p__commode
ms.assetid: 4380acb8-e3e4-409c-a60f-6205ac5189ce
ms.openlocfilehash: 3a565a179077635438c03539cefa83823603bb00
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62289422"
---
# <a name="pcommode"></a>__p__commode

İşaret `_commode` varsayılan belirtir genel değişkeni *dosya işleme modu* dosya g/ç işlemleri için.

## <a name="syntax"></a>Sözdizimi

```cpp
int * __p__commode(
   );
```

## <a name="return-value"></a>Dönüş Değeri

İşaretçi `_commode` genel değişkeni.

## <a name="remarks"></a>Açıklamalar

`__p__commode` İşlevi yalnızca dahili kullanım içindir ve kullanıcı kodundan çağrılmamalıdır.

Dosya İşleme modunu belirtir, kritik veriler yazılır diske. Daha fazla bilgi için [fflush](../c-runtime-library/reference/fflush.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|__p\__commode|internal.h|