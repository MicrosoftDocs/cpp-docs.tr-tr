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
ms.openlocfilehash: dac74085278418153ddec502f6257ce13885704d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394383"
---
# <a name="progressreporter-class"></a>progress_reporter Sınıfı

İlerleme Raporlayıcısı belirli bir türdeki ilerleme bildirimlerinin raporlama sağlar. Her progress_reporter nesnesi, bir belirli bir zaman uyumsuz eyleme veya işleme bağlıdır.

## <a name="syntax"></a>Sözdizimi

```
template<typename _ProgressType>
class progress_reporter;
```

#### <a name="parameters"></a>Parametreler

*_ProgressType*<br/>
İlerleme Raporlayıcısı ile bildirilen her bir ilerleme bildiriminin yük türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[progress_reporter](#ctor)||

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Rapor](#report)|Zaman uyumsuz eylem ya da bu işlem raporcusunun bağlı olduğu işleme bir İlerleme raporu gönderir.|

## <a name="remarks"></a>Açıklamalar

Bu tür, yalnızca Windows çalışma zamanı uygulamaları için kullanılabilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`progress_reporter`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ppltasks.h

**Namespace:** eşzamanlılık

##  <a name="ctor"></a> progress_reporter

```
progress_reporter();
```

##  <a name="report"></a> Rapor

Zaman uyumsuz eylem ya da bu işlem raporcusunun bağlı olduğu işleme bir İlerleme raporu gönderir.

```
void report(const _ProgressType& val) const;
```

### <a name="parameters"></a>Parametreler

*VAL*<br/>
Devam eden bildirim yoluyla bildirilecek yük.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
