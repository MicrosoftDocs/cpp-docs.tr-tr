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
ms.openlocfilehash: 31979a3181dc57644f1e6877277884e55cebf733
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80170948"
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
