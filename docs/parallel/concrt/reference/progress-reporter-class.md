---
title: progress_reporter Sınıfı
ms.date: 11/04/2016
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
ms.openlocfilehash: bd8f50a8c9829ff9de3e2412b89aa4de88d90db6
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77138767"
---
# <a name="progress_reporter-class"></a>progress_reporter Sınıfı

Progress Reporter sınıfı, belirli bir türdeki ilerleme bildirimlerinin raporlanmasını sağlar. Her progress_reporter nesnesi belirli bir zaman uyumsuz eyleme veya işleme bağlanır.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename _ProgressType>
class progress_reporter;
```

### <a name="parameters"></a>Parametreler

*_ProgressType*<br/>
İlerleme durumu Raporlayıcı aracılığıyla bildirilen her ilerleme bildiriminin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[raporlamak](#report)|Bu Progress Reporter 'ın bağlandığı zaman uyumsuz eyleme veya işleme bir ilerleme raporu gönderir.|

## <a name="remarks"></a>Açıklamalar

Bu tür yalnızca Windows Çalışma Zamanı uygulamalar tarafından kullanılabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`progress_reporter`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** ppltasks. h

**Ad alanı:** eşzamanlılık

## <a name="ctor"></a>progress_reporter

```cpp
progress_reporter();
```

## <a name="report"></a>raporlamak

Bu Progress Reporter 'ın bağlandığı zaman uyumsuz eyleme veya işleme bir ilerleme raporu gönderir.

```cpp
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>Parametreler

*Acil*<br/>
İlerleme bildirimiyle raporlamak için yük.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
