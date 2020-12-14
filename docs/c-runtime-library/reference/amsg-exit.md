---
description: 'Hakkında daha fazla bilgi edinin: _amsg_exit'
title: _amsg_exit
ms.date: 11/04/2016
api_name:
- _amsg_exit
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _amsg_exit
helpviewer_keywords:
- _amsg_exit
ms.assetid: 146d4faf-d763-43a4-b264-12711196456b
ms.openlocfilehash: d00283f3222a217db8337129f66b377f7c0d494e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211407"
---
# <a name="_amsg_exit"></a>_amsg_exit

Belirtilen çalışma zamanı hata iletisini yayar ve 255 hata koduyla uygulamadan çıkar.

## <a name="syntax"></a>Sözdizimi

```cpp
void _amsg_exit ( int rterrnum );
```

### <a name="parameters"></a>Parametreler

*rterrnum*<br/>
Sistem tarafından tanımlanan bir çalışma zamanı hata iletisinin kimlik numarası.

## <a name="remarks"></a>Açıklamalar

Bu işlev, konsol uygulamaları için çalışma zamanı hata iletisini **stderr** 'e yayar veya iletiyi Windows uygulamaları için bir ileti kutusunda görüntüler. Hata ayıklama modunda, çıkmadan önce hata ayıklayıcıyı çağırmayı seçebilirsiniz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|_amsg_exit|iç. h|
