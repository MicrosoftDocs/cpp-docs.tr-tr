---
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
ms.openlocfilehash: 2d577bfcf0584ef982ab43ff98674d0cfadd14ba
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939690"
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