---
title: progress_reporter sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs:
- C++
helpviewer_keywords:
- progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8dfb224fb0c0f641e4b7ef8809268fa4fad58890
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438801"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı](concurrency-namespace.md)
